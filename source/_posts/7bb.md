---
title: "力扣2022-04-10-2"
date: 2022-04-10 23:53:00
updated: 2022-04-13 18:23:24
permalink: "posts/7bb.html"
categories:
  - "数据结构与算法"
tags:
  - "算法"
  - "leetcode"
---

<h2 id="题目852-山脉数组的峰顶索引"><a href="#%E9%A2%98%E7%9B%AE852-%E5%B1%B1%E8%84%89%E6%95%B0%E7%BB%84%E7%9A%84%E5%B3%B0%E9%A1%B6%E7%B4%A2%E5%BC%95" class="headerlink" title="题目852.山脉数组的峰顶索引"></a>题目852.山脉数组的峰顶索引</h2><p>难度：简单</p>
<p><strong>山脉数组</strong><code>arr</code></p>
<ul>
<li>arr.length &gt;= 3</li>
<li>存在 i（0 &lt; i &lt; arr.length - 1）使得：  <ul>
      <li>arr[0] &lt; arr[1] &lt; ... arr[i-1] &lt; arr[i] </li>
      <li>arr[i] &gt; arr[i+1] &gt; ... &gt; arr[arr.length - 1]</li>
  </ul></li>
</ul>
<p>给你由整数组成的山脉数组 arr ，返回任何满足 arr[0] &lt; arr[1] &lt; … arr[i - 1] &lt; arr[i] &gt; arr[i + 1] &gt; … &gt; arr[arr.length - 1] 的下标 i 。</p>
<p><strong>示例 1：</strong></p>
<pre class="line-numbers language-none"><code class="language-none">输入：arr = [0,1,0]
输出：1
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre>


<p><strong>示例 2：</strong></p>
<pre class="line-numbers language-none"><code class="language-none">输入：arr = [0,2,1,0]
输出：1
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre>


<p><strong>示例 3：</strong></p>
<pre class="line-numbers language-none"><code class="language-none">输入：arr = [0,10,5,2]
输出：1
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre>


<p><strong>示例 4：</strong></p>
<pre class="line-numbers language-none"><code class="language-none">输入：arr = [3,4,5,1]
输出：2
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre>


<p><strong>示例 5：</strong></p>
<pre class="line-numbers language-none"><code class="language-none">输入：arr = [24,69,100,99,79,78,67,36,26,19]
输出：2
<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span></span></code></pre>




<p><strong>提示：</strong></p>
<ul>
<li>3 &lt;= arr.length &lt;= 10<sup>4</sup></li>
<li>0 &lt;= arr[i] &lt;= 10<sup>6</sup></li>
<li>题目数据保证 arr 是一个山脉数组</li>
</ul>
<p><strong>进阶：</strong>很容易想到时间复杂度 O(n) 的解决方案，你可以设计一个 O(log(n)) 的解决方案吗？</p>
<p>来源：力扣（LeetCode）<br>链接：<a target="_blank" rel="noopener" href="https://leetcode-cn.com/problems/peak-index-in-a-mountain-array/">https://leetcode-cn.com/problems/peak-index-in-a-mountain-array/</a><br>著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。</p>
<h2 id="解题思路"><a href="#%E8%A7%A3%E9%A2%98%E6%80%9D%E8%B7%AF" class="headerlink" title="解题思路"></a>解题思路</h2><blockquote>
<ol>
<li>直接暴力法arr[i]&gt;arr[i-1]&amp;&amp;arr[i]&gt;arr[i+1]</li>
<li>二分法</li>
</ol>
<p>支持暴力法和二分法，显然二分法更快</p>
</blockquote>
<h2 id="解题代码"><a href="#%E8%A7%A3%E9%A2%98%E4%BB%A3%E7%A0%81" class="headerlink" title="解题代码"></a>解题代码</h2><pre class="line-numbers language-c++" data-language="c++"><code class="language-c++">//暴力法
class Solution {
public:
    int peakIndexInMountainArray(vector&lt;int&gt;&amp; arr) {
        if(arr[0]&gt;arr[1]){
            return 0;
        }
        for(int i=1;i&lt;arr.size()-1;i++){
            if(arr[i]&gt;arr[i-1]&amp;&amp;arr[i]&gt;arr[i+1]){
                return i;
            } 
        }
        return arr.size()-1;
    }
};<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre>

<pre class="line-numbers language-c++" data-language="c++"><code class="language-c++">class Solution {
public:
    int peakIndexInMountainArray(vector&lt;int&gt;&amp; arr) {
        // if(arr[0]&gt;arr[1]){return 0;}
        int left=0,right=arr.size()-1,mid=left+(right-left)/2;
        while(left!=right){
            if(arr[left]&lt;arr[mid]){
                right=mid;
            }else{
                left=mid+1;
            }
            mid=left+(right-left)/2;
        }
        return left;
    }
};<span aria-hidden="true" class="line-numbers-rows"><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span><span></span></span></code></pre>
