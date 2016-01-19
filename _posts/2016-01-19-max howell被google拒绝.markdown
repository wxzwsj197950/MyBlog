---
layout:     post
title:      "Max Howell面试Google输在了这题目上"
subtitle:   "反转二叉树"
date:       2016-01-19 13:09:00
author:     "Wuxx"
header-img: "img/post-bg-01.jpg"
---
## # Google: 90% of our engineers use the software you wrote (Homebrew), but you can’t invert a binary tree on a whiteboard so fuck off. # ##

我们90%的工程师都用你写的软件，但抱歉我们不能聘用你。

软件程序猿 Max Howell 在 Google 面试时遇到了让人悲伤的情境。他把这次面试经历写成了一条简短的推文：![](http://cdn.pingwest.com/wp-content/uploads/2015/06/to-invert-a-binary-tree-e1433990285549.png)Homebrew 是 Mac OS X 上的一个非常著名的软件，经过数年的发展，已经成为了 OS X 上不可或缺的套件管理器，极大地简化了 OS X 上软件安装的流程。Max Howell 在 Twitter 上说的的确没错，在所有开发 Mac OS X/iOS 软件的开发者当中，恐怕没有人不知道 Homebrew 的存在。

Howell 本人就是 Homebrew 的原作者，一名 OS X/iOS 业界知名的软件工程师，是早先著名的网络电台 Last.fm 的首席客户端开发者、Twitter 客户端 TweetDeck 的首席移动开发者——然而，很遗憾，不知道哪位不长眼的 Google 技术 HR 面试的他。根据 Howell 在 Twitter 上的对话记录，他当时是去面试一个 iOS 的职位，「我当真可以算 iOS 业界的专家了，那家伙几乎没问我任何有关 iOS 的问题。」Howell 在 Twitter 上吐槽道。
原文：[http://www.pingwest.com/sorry-cant-hire-you/](http://www.pingwest.com/sorry-cant-hire-you/)

所以来看看这道题目吧。。。（原题leetcode226）

Invert a binary tree.

         4
       /   \
  	  2     7
	 / \   / \
	1   3 6   9

to
         
           4
  		 /   \
  		7     2
 	   / \   / \
	  9   6 3   1

很简单，就是把一棵二叉树左右调换。

用递归的方法，代码如下：

    public class Solution {
     public TreeNode InvertTree(TreeNode root) {
        if(root==null) return null;
        TreeNode n = root.right;
        root.right = root.left;
        root.left = n;
        InvertTree(root.left);InvertTree(root.right);
        return root;
     }
    }
