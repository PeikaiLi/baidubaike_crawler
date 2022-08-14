# baidubaike_crawler
## （1）基本思路：
利用name在百度百科中检索，同名人物利用postion与百科人物标题的文本相似度判断，选择相似度最高的。
## （2）爬虫结果：
score为在存在同名人物情况下，position与人物标题本文相似度。score=1说明百度百科中没有同名情况，直接跳转到对应主页。
需要注意的是，即便score=1，也不意味着该主页与我们需要检索的人物完全匹配（百度百科只有此一特定人名，但非我们需要的人物），
为了便于判断，新增一列position_sub，为position通过结巴分词的结果，新增一列position_in_cv_score，是position_sub中的词语在cv变量中的比例。
可依据position_in_cv_score这一变量进行判断。
此外，还增加了intro（百科人物主页简介）、profile（个人信息表格）、cv（主页主要内容）字段、url（人物主页网站）。
