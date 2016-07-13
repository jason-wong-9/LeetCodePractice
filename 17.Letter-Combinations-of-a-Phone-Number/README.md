#17. Letter Combinations of a Phone Number
Given a digit string, return all possible letter combinations that the number could represent.
```java
public List<String> letterCombinations(String digits) {
    LinkedList<String> ans = new LinkedList();
    if (digits.isEmpty()) return ans;
    String[] map = new String[] {"0", "1", "abc", "def", "ghi", "jkl", "mno", "pqrs", "tuv", "wxyz"};
    ans.add("");
    for (int i = 0; i < digits.length(); ++i){
        int x = Character.getNumericValue(digits.charAt(i));
        while (ans.peek().length() == i){
            String t = ans.remove();
            for (char s : map[x].toCharArray())
                ans.add(t + s);
        }
    }
    return ans;
}
```
