answer = [1,3] #진짜 리스트
part_answer = [] #n 값 고정되어 있고 k값 변동할때
smallest = 1000

def hanoi(n,k): #점화식 계산
    part_answer.append(int(2*(int(answer[k-1])) + 2**(n-k)-1))
    

def mininum(part_answer, smallest): #나온 값들 중 최솟값
    for num in part_answer: 
        if smallest > num:
            smallest = num
    answer.append(smallest)


b_n_number = 20 # n항까지 실행
for n in range(3,b_n_number): #
    for k in range(1, n-1):
        hanoi(n, k)
    mininum(part_answer, smallest)
    smallest = 1000
    part_answer = []

for i in range(b_n_number):
    print("b_%d = %d" %(i+1, answer[i]))



