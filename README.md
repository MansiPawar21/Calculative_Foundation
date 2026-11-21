# Calculative Foundation – Linear Algebra Project

## 1. Project Overview

This project demonstrates practical applications of **Linear Algebra** by analyzing a sample dataset of students' performance scores across four subjects: Maths, Science, English and Computer.

The project follows the tasks in the *Calculative Foundation* assignment brief. It covers vector operations, matrix operations, linear geometry, covariance, eigenvalues, eigenvectors and a PCA dimensionality-reduction demonstration.

**No external dataset is required.** The sample student dataset is created directly inside the Python code and is reused for all calculations.

## 2. Objectives

- Represent each student's subject scores as a vector.
- Calculate L1 (Norm-1) and L2 (Norm-2).
- Calculate dot products and angles between student score vectors.
- Calculate a cross product using three selected subjects.
- Find the projection of one student's vector onto another.
- Perform matrix addition, multiplication, transpose, inverse (where possible) and determinant.
- Explain lines, planes and hyperplanes in relation to the number of data dimensions.
- Calculate and interpret the covariance matrix, eigenvalues and eigenvectors.
- Demonstrate dimensionality reduction using PCA.
- Visualize student scores and variance using graphs.

## 3. Dataset

The dataset is embedded in the Python program. It contains six sample students and four subject scores:

| Student | Maths | Science | English | Computer |
| ------- | ----- | ------- | ------- | -------- |
| Amit    | 85    | 78      | 92      | 88       |
| Priya   | 72    | 90      | 80      | 75       |
| Rahul   | 95    | 85      | 89      | 93       |
| Neha    | 60    | 70      | 68      | 72       |
| Karan   | 88    | 92      | 95      | 90       |
| Riya    | 76    | 82      | 78      | 85       |

The resulting score matrix has **6 rows × 4 columns**. Rows represent students; columns represent subjects. These are sample values for demonstrating the mathematical operations, not results from an external research dataset.

## 4. Project Structure

```text
Calculative-Foundation-Project/
│
├── Calculative_Foundation.ipynb
├── calculative_foundation.py
├── Theory_Documentation.pdf
├── README.md
│
└── Screenshots/
    ├── dataset_output.png
    ├── vector_operations.png
    ├── matrix_operations.png
    ├── 2d_student_plot.png
    ├── 3d_student_plot.png
    ├── eigenvalues_output.png
    └── pca_plot.png
```

The `Screenshots` folder is recommended for storing clear screenshots of the notebook's important outputs and graphs. Use the actual filenames you create.

## 5. Concepts Implemented

### Part A – Vector and Matrix Fundamentals

1. **Student vectors:** Each student's four subject scores form a four-dimensional vector.
2. **Norm-1:** Sum of the absolute values of vector components.
3. **Norm-2:** Square root of the sum of squared vector components.
4. **Dot product:** Sum of products of corresponding vector components.
5. **Angle between vectors:** Calculated from the dot product and the two L2 norms.
6. **Cross product:** Calculated after selecting three subject scores, because the standard cross product used here is for 3D vectors.
7. **Vector projection:** Calculates the component of one vector in the direction of another.

### Part B – Matrix Operations

1. **Addition:** Adds matrices of the same shape.
2. **Multiplication:** Calculates `A @ A.T` (student-to-student dot-product matrix) and `A.T @ A` (subject-to-subject dot-product matrix).
3. **Transpose:** Interchanges rows and columns.
4. **Inverse:** The original score matrix is rectangular (6 × 4), so it has no ordinary inverse. The program checks the square matrix `A.T @ A` and calculates its inverse only if it is non-singular.
5. **Determinant:** Calculated for a square 4 × 4 matrix formed from the first four students.

### Part C – Linear Transformations and Geometry

- **Line:** One-dimensional representation.
- **Plane:** Two-dimensional representation, such as Maths versus Science.
- **Hyperplane:** An (n−1)-dimensional flat subspace in an n-dimensional space.
- The program plots the first two subjects in 2D and the first three subjects in 3D. The complete dataset has four subject dimensions.

### Part D – Eigenvalues and Decomposition

- Calculates the covariance matrix of the four subject variables.
- Calculates eigenvalues and eigenvectors of the covariance matrix.
- Sorts eigenvalues from largest to smallest.
- Calculates the percentage of variance explained by each component.
- Displays a bar chart of variance explained.

### PCA – Additional Dimensionality-Reduction Demonstration

The PCA section centers the subject-score data, selects the first two principal directions and projects the original four-dimensional data into two dimensions. It prints the original and reduced shapes and plots the transformed student points.

## 6. Technologies and Libraries

- **Python 3** – Main programming language.
- **NumPy** – Numerical arrays, vector and matrix calculations, covariance and eigen decomposition.
- **Pandas** – Dataset creation and tabular display.
- **Matplotlib** – 2D, 3D and bar-chart visualizations.
- **Jupyter Notebook** – Interactive practical implementation.

## 7. Installation

Install the required libraries using:

```bash
pip install numpy pandas matplotlib
```

If you use Google Colab, these commonly used libraries are generally already available. If a missing-library error occurs, run the installation command in a notebook cell.

## 8. How to Run the Project

### Option A – Jupyter Notebook

1. Download or clone this GitHub repository.
2. Open a terminal in the project folder.
3. Install the libraries listed above.
4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `Calculative_Foundation.ipynb`.
6. Choose **Run All** to execute the notebook from top to bottom.
7. Check the printed calculations and graphs.

### Option B – Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload `Calculative_Foundation.ipynb` from this repository.
3. Open the notebook.
4. Select **Runtime → Run all**.
5. Review the outputs and visualizations.

### Option C – Python Script

Run the `.py` file from a terminal:

```bash
python calculative_foundation.py
```

The script prints the calculations and displays the plots. The PCA section can be kept as a separate final section in the notebook or added to the `.py` file if you want the script to run that extra demonstration too.

## 9. Expected Outputs

When the code runs successfully, it displays:

- The student performance dataset and score matrix.
- Each student's score vector, Norm-1 and Norm-2.
- Dot product and angle between the selected students.
- Cross product and vector projection.
- Matrix addition, matrix products and transpose.
- Inverse check and determinant.
- 2D and 3D student performance scatter plots.
- Covariance matrix, eigenvalues and eigenvectors.
- Percentage of variance explained and its bar chart.
- PCA-reduced data and a 2D PCA scatter plot (if the optional PCA section is run).

**Note:** Exact numerical outputs are calculated by the program. The interpretation should be written below each relevant output or graph in the notebook.

## 10. Important Mathematical Notes

- The score matrix is 6 × 4, so it is not square and does not have an ordinary matrix inverse.
- The cross product is calculated using three selected subject values from each of two student vectors.
- The angle between vectors is calculated after clipping the cosine value to the interval [-1, 1] to avoid floating-point rounding issues.
- The covariance matrix is calculated with students as observations and subjects as variables.
- Eigenvalues describe variance along principal directions; they do not rank individual students.
- PCA reduces the four subject dimensions to two in this demonstration, so some variance may be lost.

## 11. Conclusion

This project demonstrates how Linear Algebra can be used to organize and analyze student performance data. It applies vector and matrix calculations, explains geometric dimensions, and uses covariance and eigen decomposition to understand variation across subjects. The PCA demonstration shows how a dataset with four subject features can be represented in two dimensions for visualization.

## 12. References

- Calculative Foundation assignment brief.
- [NumPy Documentation](https://numpy.org/doc/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Matplotlib Documentation](https://matplotlib.org/stable/)
