#Substring With Concatenation of All Words
You are given a string s and a list of words words that are all of the same length. Find all starting indices of substring(s) in s that is a concatenation of each word in words exactly once and without any intervening characters.
```java
public List<Integer> findSubstring(String S, String[] words) {
    List<Integer> result = new ArrayList();
    int size = words[0].length();
    if (words.length == 0 || words[0].isEmpty() || words[0].length() > S.length())
        return result;
    Map<String, Integer> hist = new HashMap();
    for (String w : words){
        hist.put(w, !hist.containsKey(w) ? 1 : hist.get(w) + 1);
    }
    for (int i = 0; i + size * words.length <= S.length(); i++){
        if (hist.containsKey(S.substring(i, i+size))){
            Map<String, Integer> currHist = new HashMap();
            for (int j = 0; j < words.length; j++){
                String word = S.substring(i+j*size, i + (j+1)*size);
                currHist.put(word, !currHist.containsKey(word) ? 1 : currHist.get(word) + 1);
            }
            if (currHist.equals(hist)) result.add(i);
        }
    }
    return result;
}
```
