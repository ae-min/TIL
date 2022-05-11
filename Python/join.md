# ' '.join(리스트)


    a = ['A','B','C','D']
    s1 = ''.join(a)
    s2 = ','.join(a)
    s3 = '/'.join(a)

    출력 결과 :
    s1 : ABCD (공백없이 하나의 문자열로 반환)
    s2 : A,B,C,D
    s3 : A/B/C/D


# 숫자리스트를 문자열로 변환 후 join

    print(' '.join(map(str, answer))) #리스트로 입력받은 숫자요소들을 str문자열로 변환 후, join을 적용해 하나의 문자열로 출력 
