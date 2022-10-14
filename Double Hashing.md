```java
1.  import java.util.Scanner;  
2.  import java.math.*;  
3.  /* Class LinkedHashEntry */  
4.  class HashEntry  
5.  {  
6.      String key;  
7.      int value;  

9.     /* Constructor */  
10.      HashEntry(String key, int value)  
11.      {  
12.          this.key = key;  
13.          this.value = value;  
14.      }  
15.  }  

17.  /* Class HashTable */  
18.  class HashTable  
19.  {  
20.      private int TABLE_SIZE;  
21.      private int size;  
22.      private HashEntry[] table;  
23.      private int primeSize;  

25.     /* Constructor */  
26.      public HashTable(int ts)  
27.      {  
28.          size = 0;  
29.          TABLE_SIZE = ts;  
30.          table = new HashEntry[TABLE_SIZE];  
31.          for (int i = 0; i < TABLE_SIZE; i++)  
32.              table[i] = null;  
33.          primeSize = getPrime();  
34.      }  
35.     /* Function to get prime number less than table size for myhash2 function */  
36.      public int getPrime()  
37.      {  
38.          for (int i = TABLE_SIZE - 1; i >= 1; i--)  
39.              {  
40.                  int fact = 0;  
41.                  for (int j = 2; j <= (int) Math.sqrt(i); j++)  
42.                      if (i % j == 0)  
43.                          fact++;  
44.                  if (fact == 0)  
45.                      return i;  
46.              }  
47.         /* Return a prime number */  
48.          return 3;  
49.      }  
50.     /* Function to get number of key-value pairs */  
51.      public int getSize()  
52.      {  
53.          return size;  
54.      }  
55.      public boolean isEmpty()  
56.      {  
57.          return size == 0;  
58.      }  
59.     /* Function to clear hash table */  
60.      public void makeEmpty()  
61.      {  
62.          size = 0;  
63.          for (int i = 0; i < TABLE_SIZE; i++)  
64.              table[i] = null;  
65.      }  
66.     /* Function to get value of a key */  
67.      public int get(String key)  
68.      {  
69.          int hash1 = myhash1( key );  
70.          int hash2 = myhash2( key );  
71.          while (table[hash1] != null && !table[hash1].key.equals(key))  
72.              {  
73.                  hash1 += hash2;  
74.                  hash1 %= TABLE_SIZE;  
75.              }  
76.          return table[hash1].value;  
77.      }  
78.     /* Function to insert a key value pair */  
79.      public void insert(String key, int value)  
80.      {  
81.          if (size == TABLE_SIZE)  
82.              {  
83.                  System.out.println("Table full");  
84.                  return;  
85.              }  
86.          int hash1 = myhash1( key );  
87.          int hash2 = myhash2( key );  
88.          while (table[hash1] != null)  
89.              {  
90.                  hash1 += hash2;  
91.                  hash1 %= TABLE_SIZE;  
92.              }  
93.          table[hash1] = new HashEntry(key, value);  
94.          size++;  
95.      }  
96.     /* Function to remove a key */  
97.      public void remove(String key)  
98.      {  
99.          int hash1 = myhash1( key );  
100.          int hash2 = myhash2( key );  
101.          while (table[hash1] != null && !table[hash1].key.equals(key))  
102.              {  
103.                  hash1 += hash2;  
104.                  hash1 %= TABLE_SIZE;  
105.              }  
106.          table[hash1] = null;  
107.          size--;  
108.      }  
109.     /* Function myhash which gives a hash value for a given string */  
110.      private int myhash1(String x )  
111.      {  
112.          int hashVal = x.hashCode( );  
113.          hashVal %= TABLE_SIZE;  
114.          if (hashVal < 0)  
115.              hashVal += TABLE_SIZE;  
116.          return hashVal;  
117.      }  
118.     /* Function myhash function for double hashing */  
119.      private int myhash2(String x )  
120.      {  
121.          int hashVal = x.hashCode( );  
122.          hashVal %= TABLE_SIZE;  
123.          if (hashVal < 0)  
124.              hashVal += TABLE_SIZE;  
125.          return primeSize - hashVal % primeSize;  
126.      }  
127.     /* Function to print hash table */  
128.      public void printHashTable()  
129.      {  
130.          System.out.println("\nHash Table");  
131.          for (int i = 0; i < TABLE_SIZE; i++)  
132.              if (table[i] != null)  
133.                  System.out.println(table[i].key +" "+table[i].value);  
134.      }  
135.  }  

137.  /* Class DoubleHashingHashTableTest */  
138.  public class DoubleHashingHashTableTest  
139.  {  
140.      public static void main(String[] args)  
141.      {  
142.          Scanner scan = new Scanner(System.in);  
143.          System.out.println("Hash Table Test\n\n");  
144.          System.out.println("Enter size");  
145.         /* Make object of HashTable */  
146.          HashTable ht = new HashTable(scan.nextInt() );  
147.          char ch;  
148.         /*  Perform HashTable operations  */  
149.          do  
150.              {  
151.                  System.out.println("\nHash Table Operations\n");  
152.                  System.out.println("1. insert ");  
153.                  System.out.println("2. remove");  
154.                  System.out.println("3. get");  
155.                  System.out.println("4. check empty");  
156.                  System.out.println("5. clear");  
157.                  System.out.println("6. size");  
158.                  int choice = scan.nextInt();  
159.                  switch (choice)  
160.                      {  
161.                      case 1 :  
162.                          System.out.println("Enter key and value");  
163.                          ht.insert(scan.next(), scan.nextInt() );  
164.                          break;  
165.                      case 2 :  
166.                          System.out.println("Enter key");  
167.                          ht.remove( scan.next() );  
168.                          break;  
169.                      case 3 :  
170.                          System.out.println("Enter key");  
171.                          System.out.println("Value = "+ ht.get( scan.next() ));  
172.                          break;  
173.                      case 4 :  
174.                          System.out.println("Empty Status " +ht.isEmpty());  
175.                          break;  
176.                      case 5 :  
177.                          ht.makeEmpty();  
178.                          System.out.println("Hash Table Cleared\n");  
179.                          break;  
180.                      case 6 :  
181.                          System.out.println("Size = "+ ht.getSize() );  
182.                          break;  
183.                      default :  
184.                          System.out.println("Wrong Entry\n ");  
185.                          break;  
186.                      }  
187.                 /* Display hash table */  
188.                  ht.printHashTable();  
189.                  System.out.println("\nDo you want to continue (Type y or n)\n");  
190.                  ch = scan.next().charAt(0);  
191.              }  
192.          while (ch == 'Y'|| ch == 'y');  
193.      }  
194.  }
```