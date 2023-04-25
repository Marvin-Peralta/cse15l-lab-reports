# **CSE15L Lab Report 2**
## By Marvin Peralta, A17271264

### **Part 1**



### **Part 2**

`class EvenExample {
  static int sumEvenIndices(int[] num) {
    int sum = 0;
    for(int i = 0; i < nums.length; i += 2) {
      sum += nums[i + 1];
    }
    return sum;
  }
}`

`public void testSumEvenLength5() {
  int[] input1 = { 12, 13, 7, 2, 33};
  assertEquals(EvenExamples.sumEvenIndices(input1), 52);
}`
This test failed.

`public void testSumEvenLength6() {
  int[] input1 = { 12, 13, 7, 8, 5, 3};
  assertEquals(EvensExamples.sumEvenIndices(input1), 24);
}`
This test passed.




### **Part 3**

