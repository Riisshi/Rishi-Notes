![[Pasted image 20250813115034.png]]
![[Pasted image 20250813115312.png]]
![[Pasted image 20250813115507.png]]
![[Pasted image 20250813115628.png]]
![[Pasted image 20250813115824.png]]
![[Pasted image 20250813120021.png]]
![[Pasted image 20250813120144.png]]
![[Pasted image 20250813120654.png]]
![[Pasted image 20250813120923.png]]
![[Pasted image 20250813143932.png]]
![[Pasted image 20250813144614.png]]
![[Pasted image 20250813145037.png]]
![[Pasted image 20250813145657.png]]
![[Pasted image 20250813150028.png]]
![[Pasted image 20250813152615.png]]
![[Pasted image 20250813154036.png]]
![[Pasted image 20250813162642.png]]
![[Pasted image 20250816094652.png]]
![[Pasted image 20250816095032.png]]
![[Pasted image 20250816100439.png]]
![[Pasted image 20250816100343.png]]
![[Pasted image 20250816100440.png]]
![[Pasted image 20250816100528.png]]
![[Pasted image 20250816100636.png]]
![[Pasted image 20250816101244.png]]
![[Pasted image 20250816101434.png]]
![[Pasted image 20250816105315.png]]
![[Pasted image 20250816105500.png]]
![[Pasted image 20250816105950.png]]
![[Pasted image 20250816110345.png]]
![[Pasted image 20250816110730.png]]
![[Pasted image 20250816112021.png]]
![[Pasted image 20250816113046.png]]
![[Pasted image 20250816113915.png]]
### Fixed Code:

```c++
#include <iostream>
using namespace std;
int gcd(int a, int b) {
	while (b != 0) {
		int temp = b;
        b = a % b;         
        a = temp;     
    }     
return a;
}  
long long lcm(int a, int b) {
	if (a == 0 || b == 0) return 0;   // handle zero case     
		return (1LL * a * b) / gcd(a, b); // use long long to avoid overflow }  
int main() {
	int x, y;     
	cin >> x >> y;     
	cout << lcm(x, y) << endl;     
	return 0; 
}
```
![[Pasted image 20250816115654.png]]
![[Pasted image 20250818154906.png]]
![[Pasted image 20250818155923.png]]
![[Pasted image 20250819093037.png]]
![[Pasted image 20250819093759.png]]
![[Pasted image 20250819094549.png]]
![[Pasted image 20250820110924.png]]
![[Pasted image 20250820111251.png]]
![[Pasted image 20250820111916.png]]
![[Pasted image 20250820112718.png]]
![[Pasted image 20250820113714.png]]
![[Pasted image 20250820120606.png]]
![[Pasted image 20250820122135.png]]
![[Pasted image 20250820122400.png]]
![[Pasted image 20250820183251.png]]
![[Pasted image 20250820184356.png]]
![[Pasted image 20250820185530.png]]
![[Pasted image 20250820185846.png]]
![[Pasted image 20250820193457.png]]
![[Pasted image 20250820194027.png]]
![[Pasted image 20250820215750.png]]
![[Pasted image 20250820220051.png]]
![[Pasted image 20250820220440.png]]
![[Pasted image 20250820220809.png]]
![[Pasted image 20250820221309.png]]
![[Pasted image 20250820222054.png]]
![[Pasted image 20250820222304.png]]
![[Pasted image 20250820223035.png]]
![[Pasted image 20250820223653.png]]
![[Pasted image 20250820224312.png]]
![[Pasted image 20250821095726.png]]
![[Pasted image 20250822122555.png]]
![[Pasted image 20250822125730.png]]
![[Pasted image 20250822130745.png]]
![[Pasted image 20250822133422.png]]
![[Pasted image 20250822170957.png]]
![[Pasted image 20250823201755.png]]
![[Pasted image 20250823201948.png]]
![[Pasted image 20250909104219.png]]
![[Pasted image 20250909110949.png]]