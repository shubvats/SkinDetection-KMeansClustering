Function kmeansfn(imageArray, kValues, tolerance)
for kIdx = 1:length(kValues)
numClusters = kValues(kIdx);
for imageIdx = 1:length(imageArray)
% Read the image, get its dimensions, choose random k
% centroids, perform k means and display 3D Matrix result
inputImage = imread(imageArray{imageIdx});
[height, width, ~] = size(inputImage);
pixelMatrix = double(reshape(inputImage, height * width, 3));
centroids = pixelMatrix(randi([1, size(pixelMatrix, 1)], numClusters,
1), :);
options = statset('TolFun', tolerance);
[clusterIdx, ~, ~, ~] = kmeans(pixelMatrix, numClusters, 'Start',
centroids, 'Options', options);
clusteredImage = reshape(clusterIdx, height, width);
displayResults(inputImage, clusteredImage, numClusters,
imageArray{imageIdx});
end
end
end
function displayResults(inputImage, clusteredImage, numClusters, imageName)
% Display the original image, construct and display heatmap
figure;
subplot(1, 2, 1);
imshow(uint8(inputImage));
title(['Original Image: ']);
heatmap = zeros(size(inputImage));
colors = rand(numClusters, 3) * 255;
for i = 1:numClusters
color = colors(i, :);
for j = 1:3
channel = heatmap(:, :, j);
channel(clusteredImage == i) = color(j);
heatmap(:, :, j) = channel;
end
end
heatmap = uint8(heatmap);
subplot(1, 2, 2);
imshow(heatmap);
title(['Heat Map (k=' num2str(numClusters) ]);
end
