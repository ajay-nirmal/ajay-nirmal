% CHIPRIDE Youtube Channel
% Hybrid Median Filter 
clc;clear;close all;
pkg load image
 %hybrid median filter
im=imread('noisyboard.jpg'); %add your image path within the quotes
k=1;
hwin=2*k+1;
im2=padarray(im,[k k],'replicate');
n=3;
[r c]=size(im);
%X Mask
x=zeros(3,3);
x(1:n+1:n*n)=1;
x(n:n-1:n*n-1)=1;
%plus mask
plus=zeros(hwin,hwin)
plus(:,2)=1;plus(2,:)=1

xfindval=find(x);     % x pixel's position
plus_find=find(plus); % plus pixel's position

for p=1:r
    for q=1:c
       w=im2(p:p+(hwin-1),q:q+(hwin-1)); %sliding window/filter
       sw=w(:)';                    % sliding window elements
       
       x_val=w(xfindval)';
       plus_val=w(plus_find)';
       
       c_val=w(5);     % original pixel/centre pixel of the window/filter
       
       M1=ceil(median(x_val));
       M2=ceil(median(plus_val));
       M3=ceil(c_val);
       res_med=[M1,M2,M3];
       out(p,q)=uint8(median(res_med));
    end
end

 subplot(1,2,1),imshow(im)
 title('original image')
 subplot(1,2,2),imshow(out)
 title('Filtered Image output')
 











