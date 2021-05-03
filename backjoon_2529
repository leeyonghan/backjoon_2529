#include<iostream>
using namespace std;
#include<vector>
#include<string>
#include<queue>
vector<bool> visit(11, false);
vector<int> number(11, 0);
string Inequality;
vector<string>result;
int T;
#include<sstream>

void dfs(int cnt, int num, string re) {
	if (cnt == T) {
		result.push_back((re));
	}
	else if (cnt < T) {
		for (int i = 0; i < 10; i++) {
			if (Inequality[cnt] == '>' && visit[i] == false && i < num) {
				visit[i] = true;
				dfs(cnt + 1, i, re + to_string(i));
				visit[i] = false;
			}
			else if (Inequality[cnt] == '<' && visit[i] == false && i > num) {
				visit[i] = true;
				dfs(cnt + 1, i, re + to_string(i));
				visit[i] = false;
			}
		}
	}
}
int main() {

	cin >> T;
	Inequality = cin.get();
	getline(cin, Inequality);
	for (int i = 0; i < Inequality.size(); i++) {
		if (Inequality[i] == ' ') {
			int copy_i = i;
			for (int j = i + 1; j < Inequality.size() ; j++,copy_i++) {
				Inequality[copy_i] = Inequality[j];
				Inequality[j] = ' ';
			}
		}
	}
	for (int i = 0; i < 10; i++) {
		number[i] = i;
	}
	for (int i = 0; i < 10; i++) {
		visit[i] = true;
		dfs(0, i, to_string(i));
		visit[i] = false;
	}
	//	cout.width((T + 1));
	//	cout.fill('0');

	cout << result[result.size() - 1] << endl << result[0] << endl;
	return 0;
}
