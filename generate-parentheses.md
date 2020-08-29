# [generate-parentheses](https://leetcode-cn.com/problems/generate-parentheses/)

# #1



~~~java
class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> result = new ArrayList<>();
        generate(0,0, n,"",result);
        return result;
    }

    private void generate(int left,int right,int max,String s,List<String> result) {
        if (left == max && right == max) {
            result.add(s);
            return;
        }
        if (left < max) {
            generate(left+1, right, max,s+'(',result);
        }
        if (left > right) {
            generate(left,right+1,max,s+')',result);
        }
    }
}
~~~

