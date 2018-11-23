# Highly divisible triangular number
# Find the value of the first triangle number to have over n divisors

import time
_start_time = time.time()
_divisors_limit = 500


def get_triangular(_num):
	_triang = 0
	for i in range(_num):
		_triang += i
	return _triang

def get_factor_count(_num):
	_counter = 1
	for i in range(1,_num/2 +1):
		if _num%i == 0:
			_counter += 1
	return _counter

if __name__ == '__main__':
	_num = 1;_fact_count =1
	while _fact_count <= _divisors_limit:
		_temp = get_triangular(_num)
		_fact_count = get_factor_count(_temp)
		_num += 1
	print 'Count achieved @ %d ' % (_temp)
	print 'Computed in %f ' % (time.time()-_start_time)
