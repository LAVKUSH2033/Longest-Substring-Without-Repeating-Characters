# Longest-Substring-Without-Repeating-Characters
solution
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
          int n =s.length();
          int left =0 ,right =0,maxlen=0;
          unordered_set<char> set;
          while(right<n){
              if(set.count(s[right])==0)
              {
                  set.insert(s[right]);
                  maxlen =max(maxlen, right-left +1);
                  right++;
              }
              else
              {
                  set.erase(s[left]);
                  left++;
              }
          }
          return maxlen;
    }
};
