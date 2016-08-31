1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異
  Ans:任何整數都是Fixnum物件，中間帶有點號的就是浮點數

2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```
  Ans:用 + 號連接字串會多耗記憶體，所以可以用字串內差(string interpolation)的方式連接字串

3. 請解釋 array 和 hash 的不同處
  Ans:
  array是一種資料結構，可以把它想像成儲存許多值的清單，可以在裡面塞很多不同型別的資料
  hash另一種資料結構，可以把他想像成置物箱，每一個值(value)會對應到一個鑰匙(key)

4. 請用一行程式碼從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值
  Ans:
  ```ruby
  [1, "a string", 3.14, [1,2,3,4]].select {|x| x.is_a?(Numeric)}
  ```

5. 請用一行程式碼把一個內容為整數 1 到 100 的陣列裡所有的值加上 2
  Ans:
  ```ruby
  (1..100).map {|x| x + 2}
  ```

6. 請寫出以下兩行程式碼迴傳的值，並解釋他們呼叫的方法差別為何：

  ```ruby
  [1, 2, 3, 3].uniq
  [1, 2, 3, 3].uniq!
  ```
  Ans:任何加 ! 的方法代表呼叫該方法的物件最後會被改變
  ```ruby
  arr = [1, 2, 3, 3]
  arr.uniq
  # =>[1, 2, 3]
  puts "#{arr}"
  # =>[1, 2, 3, 3]
  
  arr.uniq!
  # =>[1, 2, 3]
  puts "#{arr}"
  # =>[1, 2, 3]
  ```

7. 請列出兩種產出亂數的方法
  Ans:
  ```ruby
  [1, 2, 3, 4, 5].sample
  [1, 2, 3, 4, 5].shuffle.pop
  ```

8. 以下這段程式碼：

  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
會執行出什麼結果？ 請試試不用 irb 算出結果
  Ans:結果為true
  (1 > 3) => false
  (true == true) => true
  (false && true) => false
  (!!!false) => true
  false || true => true

9. 請問 binding.pry 是什麼？ 要如何使用它？
  Ans:
  Ruby 語言的除錯工具，在程式的最上方寫 require 'pry'，
  binding.pry 等於在 ruby 的程式碼裡面下斷點，程式執行到此就會停住

10. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

  ```ruby
  var = 5

  if var >= 5
    return "var is greater than or equal to 5"
  else
    return "var is less than 5"
  end
  ```
  Ans:
  ```ruby
  puts var >= 5 ? "var is greater than or equal to 5" : "var is less than 5"
  ```

11. 請列出兩種不同的 hash 寫法
  Ans:
  ```ruby
  student = { 
             :name => "Ruby", 
             :score => 60,
           }
  
  student = { 
             name: "Ruby", 
             Score: 60,
           }  
  ```