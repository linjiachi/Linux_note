* [Shell Script 腳本](https://github.com/linjiachi/Linux_note/blob/master/108-2/Shell%20Script.md#shell-script-%E8%85%B3%E6%9C%AC)

---
# Shell Script 腳本
* Shell 是一種讓使用者可以和作業系統 Kernal 更新互動溝通的橋樑
* Shell Script 主要是使用在 Linux 和 MacOS 等自動化操作指令的程式語言
* 我們通常使用 `.sh` 副檔名來命名 Shell Script 檔案

## 
### 1. if
* if 開頭，if 結尾
* == 和 != 通常用來做文字、字串的判斷
* 數字判斷使用
    - -eq：equal，相等
    - -ne：not equal，不相等
    - -gt：greater than，大於
    - -lt：less than，小於
    - -ge：greater equal，大於等於
    - -le：less equal，小於等於
* 文字變數最好加上雙引號，不然字串有空格時會有問題
* exit：程式結束，可在 exit 加上數字

#### 範例一 - 判斷字串x是否等於字串y
```sh
if [ "$x" == "$y" ]; then
   echo x "is equal to " y
fi
```
#### 範例二 - 判斷是否有打指令
```sh
if [ $# -ne 1 ]; then
   echo "`basename $0` domain_name (e.g. `basename $0` www.pchome.com.tw)"
   exit 1
fi
```
#### 範例三 - 判斷是否為超級使用者
```sh
if [ $UID -eq 0 ]; then
   echo "don't use root to run this program"
   exit 2
fi
```

### 2. awk
* 搜尋最近的三個程序的 PID 並進行排序 `ps | awk '{print $1}' | sort -rn | tail -3`

    ```sh
    [root@vm1 user]# ps | awk '{print $1}' | sort -rn | tail -3
    3096
    3092
    PID
    ```
* `answer=$(host $name | awk '{print $4}')`
    - `host [-a] hostname`：查某個主機名稱的 IP
        - `-a`：列出詳細資訊
    ```sh
    [root@vm1 user]# host www.google.com
    www.google.com has address 216.58.200.36
    www.google.com has IPv6 address 2404:6800:4008:802::2004
    ```
### 3. 運算式
* expr裡的變數要用空白隔開，並且不能使用小數
* 乘法要使用跳脫字元 `\*`
* 處理小數需使用 bc
```sh
b=`expr 5 + 2`
echo $b
echo `expr 5 \* 2` 
let a+=1
echo 5.0*1.2+3.4 | bc
```
### 4. case
* case 開頭，esac 結尾
* ;; 等同於結束
```sh
language='Java'

case $language in
   Java*) echo "是 Java！"
         ;;
   Python*) echo "是 Python！"
         ;;
   C*)     echo "是 C！"
         ;;
   *)      echo "沒 match 到！"
esac
```
### 5. for
* `{1..5..2}`：{ 起始值..終止值..間隔 }，執行結果 1 3 5
#### 範例一
```sh
for loop in {1..5..2}; do     # {}
 echo "number: $loop"
done
for loop in $(1..5..2); do    # $()
 echo "number: $loop"
done
for loop in ((1..5..2)); do   # (( ))
 echo "number: $loop"
done
```
### 6. do
* do 開頭，done 結尾
#### 範例一
```sh
for loop in {1..5..2}; do
 echo "number: $loop"
done
```
### 7. while
#### 範例一
```sh
counter=0
while [ $counter -le 5 ]; do
   counter=`expr $counter + 1`
   echo $counter
done
```
#### 範例二
```sh
while read line
do
   ping -c1 -W1 $line &>/dev/null   # 把訊息丟入空
   if [ $? -eq 0 ];then
      echo $line "is ok"
   else
      echo $line "is not ok"
   fi
done < ip.txt  # 讀 ip.txt 檔案中的資料
```
* 讀檔，將檔名寫在 done 之後，使用 read 將會一行一行讀取
### 8. continue
#### 範例一
```sh
for loop in {1..5}; do
    if [$loop -eq 3]; then
       continue
    fi
    echo "number: $loop"
done
```
### 9. until
* 易出錯，小心使用
#### 範例一
```sh
counter=0
until [ $counter -gt 10 ]; do
   echo $counter
   counter=`expr $counter + 1`
done
```
### 10. function
* Linux 的 function 傳入值要在呼叫函式後輸入
#### 範例一
```sh
function echoHello() {
 # hello world, rock!!
 echo "${0} hello ${1}, ${2}!!"
}

echoHello 'world' 'rock'

echo ${0}   # 目前檔案的名稱
echo ${1}   # 指外部指令的參數，而非本檔案內參數
echo ${2}

echo ${#}   # 用來統計輸入有多少個參數
echo ${*}   # 用來顯示所有參數
echo ${@}   # 用來顯示所有參數
```










---
參考資料：
* [簡明 Linux Shell Script 入門教學](https://blog.techbridge.cc/2019/11/15/linux-shell-script-tutorial/)
* [第十二章、學習 Shell Scripts](http://linux.vbird.org/linux_basic/0340bashshell-scripts.php#script)
* [第十九章、主機名稱控制者： DNS 伺服器](http://linux.vbird.org/linux_server/0350dns.php)
