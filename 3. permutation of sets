#include <iostream>
#include <vector>

using namespace std;

// Function to swap two elements in a vector

void swap(vector<int>& nums, int i, int j) {
  int temp = nums[i];
  nums[i] = nums[j];
  nums[j] = temp;
}

// Function to generate all permutations with repetition

void Generate__Permutations__With__Repetition(vector<int>& nums, vector<int>& perm, int length) {
  // If permutation is complete, print it
  
  if (perm.size() == length) {
    for (int num : perm) {
      cout << num << " ";
    }
    cout << endl;
    return;
  }

  // Generate permutations recursively
  
  for (int i = 0; i < nums.size(); i++) {
    perm.push_back(nums[i]);
    Generate__Permutations__With__Repetition(nums, perm, length);
    perm.pop_back();
  }
}

// Function to generate all permutations without repetition

void Generate__Permutations__Without__Repetition(vector<int>& nums, vector<int>& perm, vector<bool>& used) {
    
  // If permutation is complete, print it
  
  if (perm.size() == nums.size()) {
    for (int num : perm) {
      cout << num << " ";
    }
    cout << endl;
    return;
  }

  // Generate permutations recursively
  
  for (int i = 0; i < nums.size(); i++) {
    if (!used[i]) {
      used[i] = true;
      perm.push_back(nums[i]);
      Generate__Permutations__Without__Repetition(nums, perm, used);
      perm.pop_back();
      used[i] = false;
    }
  }
}

// Function to generate all permutations (with or without repetition)

void Generate__Permutations(vector<int>& nums, bool withRepetition) {
  vector<int> perm;
  vector<bool> used(nums.size(), false);

  if (withRepetition) {
      
    // Generate permutations with repetition
    
    Generate__Permutations__With__Repetition(nums, perm, nums.size());
  } else {
      
    // Generate permutations without repetition
    
    Generate__Permutations__Without__Repetition(nums, perm, used);
  }
}

int main() {
    
  // Create a vector of numbers
  
  vector<int> nums = {7,8,9};

  // Generate and print all permutations with repetition
  
  cout << "Permutations with repetition:" << endl;
  Generate__Permutations(nums, true);

  // Generate and print all permutations without repetition
  
  cout << "Permutations without repetition:" << endl;
  Generate__Permutations(nums, false);

  return 0;
}
