#include <iostream>
#include <vector>

class Set {
private:
    std::vector<int> elements;

public:
    Set(std::vector<int> inputElements) {
        elements = inputElements;
    }

    void generatePowerSet(std::vector<std::vector<int>>& result, std::vector<int>& subset, int index) {
        result.push_back(subset);

        for (int i = index; i < elements.size(); i++) {
            subset.push_back(elements[i]);
            generatePowerSet(result, subset, i + 1);
            subset.pop_back();
        }
    }

    std::vector<std::vector<int>> powerSet() {
        std::vector<std::vector<int>> result;
        std::vector<int> subset;

        generatePowerSet(result, subset, 0);

        return result;
    }
};

int main() {
    std::vector<int> inputSet = {1, 2, 3};
    Set mySet(inputSet);

    std::vector<std::vector<int>> powerSet = mySet.powerSet();

    for (const auto& subset : powerSet) {
        std::cout << "{ ";
        for (const auto& element : subset) {
            std::cout << element << " ";
        }
        std::cout << "}" << std::endl;
    }

    return 0;
}
