
<pre>
def check(data):
    sum=0
    data +="0"*(0 if not len(data)%16 else 16-len(data)16)
    //判断补零
    for i in range(0,len(data),16):
        val = int(data[i:i+16],2)
        sum = sum + val
        sum = sum & 0xffffffff
        
    sum = (sum >> 16) + (sum & 0xffff)
    
    if sum > 65535:
        sum = (sum >> 16) + (sum & 0xffff)
    //高位与低位相加
 
    return 65535-sum
    //反码
a = 0b010010000110010101101100011011000110111100100001
bin(check("010010000110010101101100011011000110111100100001"))
bin(check("010010000110010101101100"))

</pre>
