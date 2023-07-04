#include <iostream>
#include <vector>
using namespace std;

class RELATION {
private:
    vector<vector<int>> matrix;
    int size;

public:
    RELATION(int n) {
        size = n;
        matrix.resize(n, vector<int>(n, 0));
    }

    void setElement(int row, int col, int value) {
        matrix[row][col] = value;
    }

    bool isReflexive() {
        for (int i = 0; i < size; i++) {
            if (matrix[i][i] != 1)
                return false;
        }
        return true;
    }

    bool isSymmetric() {
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < size; j++) {
                if (matrix[i][j] != matrix[j][i])
                    return false;
            }
        }
        return true;
    }

    bool isAntiSymmetric() {
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < size; j++) {
                if (i != j && matrix[i][j] == 1 && matrix[j][i] == 1)
                    return false;
            }
        }
        return true;
    }

    bool isTransitive() {
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < size; j++) {
                if (matrix[i][j] == 1) {
                    for (int k = 0; k < size; k++) {
                        if (matrix[j][k] == 1 && matrix[i][k] != 1)
                            return false;
                    }
                }
            }
        }
        return true;
    }

    bool isEquivalenceRelation() {
        return isReflexive() && isSymmetric() && isTransitive();
    }

    bool isPartialOrderRelation() {
        return isReflexive() && isAntiSymmetric() && isTransitive();
    }
};

int main() {
    RELATION relation(3);  // Assuming a 3x3 relation matrix

    // Setting example relation matrix elements
    relation.setElement(0, 0, 1);
    relation.setElement(0, 1, 0);
    relation.setElement(0, 2, 1);
    relation.setElement(1, 0, 0);
    relation.setElement(1, 1, 1);
    relation.setElement(1, 2, 0);
    relation.setElement(2, 0, 0);
    relation.setElement(2, 1, 1);
    relation.setElement(2, 2, 1);
    
      cout << "Is reflexive: " << relation.isReflexive() << endl;
      cout << "Is symmetric: " << relation.isSymmetric() << endl;
      cout << "Is transitive: " << relation.isTransitive() << endl;
      cout << "Is anti-symmetric: " << relation.isAntiSymmetric() << endl;

    if (relation.isEquivalenceRelation()) {
        cout << "The given relation is an Equivalence relation." << endl;
    } else if (relation.isPartialOrderRelation()) {
        cout << "The given relation is a Partial Order relation." << endl;
    } else {
        cout << "The given relation is neither an Equivalence relation nor a Partial Order relation." << endl;
    }

    return 0;
}
