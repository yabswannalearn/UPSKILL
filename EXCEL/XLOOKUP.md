xlookup ay hahanapin nya yung value ng isang cell sa isang column tapos, irereturn nya yung ka same nya ng ibang cell
so for example
hahanapin mo yung reinael sa column ng names, tapos irereturn mo yung email ng may reinael

xlookup multiple rows, dalawang column pwede mong hanapan

xlookup exact match, exact lang dapat dito, pero pwede kang gumamit ng `"*"&` meaning neto ay basta merong character na malapit don ay ssearch nya yun

xlookup search order - same lang sya pero meron syang search order, either ascending or descending

xlookup horizontal - hahanap ka naman ng pahorizontal

xlookup w sum - hahanapin nya tapos iadd panya
sample para reference
`=SUM(XLOOKUP(I1,H1:S1,H2:S2):XLOOKUP(K1,H1:S1,H2:S2))`, gamit ka ng colong sa pangalawang xlookup

