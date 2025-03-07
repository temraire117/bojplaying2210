#include <iostream>
#include <string>
#include <vector>
#include <unordered_map>

void dfs(const std::vector<std::vector<char>>& numMap, std::unordered_map<std::string, bool>& stored, std::vector<std::vector<bool>> visited, std::string& temp, int& count, int& result, int y, int x) {
    visited[y][x] = true;
    temp.push_back(numMap[y][x]);
    count++;
    if (count == 6) {
        if(stored.find(temp) == stored.end()){
            stored[temp] = true;
            result++;
        }
    temp.pop_back();
    count--;
    visited[y][x] = false;
    return;
    }
    else {
        if (y < 4) dfs(numMap, stored, visited, temp, count, result, y + 1, x);
        if (x < 4) dfs(numMap, stored, visited, temp, count, result, y, x + 1);
        if (y > 0) dfs(numMap, stored, visited, temp, count, result, y - 1, x);
        if (x > 0) dfs(numMap, stored, visited, temp, count, result, y, x - 1);
    }
    if(!temp.empty()) {
        temp.pop_back();
        count--;
    }
    visited[y][x] = false;
}
int main()
{
    std::cin.tie(nullptr);
    std::cout.tie(nullptr);
    std::ios_base::sync_with_stdio(false);
    
    std::vector<std::vector<char>> numMap(5, std::vector<char>(5));
    std::vector<std::vector<bool>> visited(5, std::vector<bool>(5, false));
    for(int i = 0; i < 5; i++) {
        if(i > 0) std::cin.ignore();
        for(int j = 0; j < 5; j++) {
            if (j > 0) std::cin.ignore();
            std::cin >> numMap[i][j];
        }
    }
    int count = 0;
    int result = 0;
    std::unordered_map<std::string, bool> stored;
    std::string temp;
    for(int i = 0; i < 5; i++) {
        for(int j = 0; j < 6; j++) dfs(numMap, stored, visited, temp, count, result, i, j);
    }

    std::cout << result;
    
}
