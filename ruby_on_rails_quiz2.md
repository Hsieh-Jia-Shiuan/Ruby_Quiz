1. 請用簡單的方式敘述以下每一行程式碼：

  ```ruby 
  a = 1 
  @a = 2
  @@a = 5
  user = User.new
  user.name
  user.name = "Joe"
  ```
  ```ruby
  Ans:
  變數a塞入整數1的數值
  實例變數a塞入整數2的數值
  類別變數a塞入整數5的數值
  User的class實體化，並被記在user裡面
  取得user裡面name得值
  將user裡面name的值改為Joe
  ```

2. 什麼是 module? 請寫一段程式碼說明一個 class 要如何使用一個 module 裡面的 method?
  ```ruby
  Ans:
  可把 module 想像成工具箱，本身並不是 class，沒有實例、不可 new，只能被 include 到其他 class 裡面使用
  module Language
    def language
      puts "can speak chinese"
    end
  end
  
  class Taiwanese
    include Language
  end

  Taiwanese.new.language
  # =>can speak chinese
  ```

3. 請說明 class variable 和 instance variable 之間的差別
  ```ruby
  Ans:
  class variable（類別變數）變數前加上 @@ 符號，範圍貫穿模組或類別以及當中定義的方法
  instance variable（實例變數）變數前加上 @ 符號，代表的是可以在同一個class的各種method之間互相傳遞
  ```

4. 請說明 class method 和 instance method 之間的差別
  ```ruby
  Ans:
  class method就是在定義method時加上self，可以直接使用
  instance method要被new出來，才能被使用
  ```

5. 如果今天我為一個叫 User 的 class 產生一個新物件的方式是:
  ```ruby
  User.new("Bob", "male", "Engineer")
  ```
請寫出 User class 的 initialize method
  ```ruby
  Ans:
  class User
    attr_accessor :name, :gender, :job
  
    def initialize(name, gender, job)
      @name = name
      @gender = gender
      @job = job
    end
  end
  ```

6. 在：
  A.  一個 class 裡，method 外面
  B.  一個 class 裡，instance method 裡
  self 分別是指向什麼?
  ```ruby
  Ans:
  A:self指向class本身
  B:self指向instance method
  ```

7. attr_accessor 的功能是什麼，它和 attr_reader、attr_writer 之間的差別是什麼？
  ```ruby
  Ans:
  attr_accessor 會幫你在 Ruby 的類別裡產生一對 getter 以及 setter 方法
  attr_reader 只會幫你產生 getter
  attr_writer 只會幫你產生 setter
  ```

8. 請說明 public 和 private method 之間的不同
  ```ruby
  Ans:
  public 就是任何屬於這個 class 的物件都能使用
  private 是只有在 class 內部才可以存取，只能在 class 裡面被其他 instance method 呼叫
  ```

9. 請說明 Inheritance 和 Module 之間的差別，它們分別是用於哪些情況？ 請舉例說明
  ```ruby
  Ans:
  你只能為一個 class 建立子類別，但卻可以 mix 很多 module
  如果今天你是需要 "是某個..." 的關係，就用 inheritance，如過需要 "擁有某項行為" 就用 module
  ```

10. 若今天有一個 class 有 include 一個 module，他的 parent class 和 sub class 是否可以使用該 module 裡的 method?
  ```ruby
  Ans:否
  module Language
    def language
      puts "can speak chinese"
    end
  end
  
  class Person 
    include Language
  
    def language 
      puts "just can speak English"
    end
  end
  
  class Taiwanese < Person
    
  end
  
  Taiwanese.new.language
  # =>just can speak English
  ```

11. 請間單說明什麼是 Relational Database，什麼是 SQL
  ```ruby
  Ans:
  Relational Database（關聯式資料庫）
  SQL結構化查詢語言
  ```