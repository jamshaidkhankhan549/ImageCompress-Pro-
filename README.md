<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ImageCompress Pro - Fast & Free Image Compression Tool</title>
    <meta name="description" content="Free online image compression tool that reduces file size while maintaining quality. Optimize JPG, PNG, and WebP images for web and mobile.">
    <meta name="keywords" content="image compression, optimize images, reduce image size, free image compressor, web image optimizer">
    <meta name="author" content="ImageCompress Pro">
    
    <!-- Open Graph tags for better social sharing -->
    <meta property="og:title" content="ImageCompress Pro - Free Online Image Compression Tool">
    <meta property="og:description" content="Compress images instantly in your browser. No uploads to servers, your data stays private.">
    <meta property="og:type" content="website">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>🖼️</text></svg>">
    
    <!-- CSS -->
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary-color: #4a6fa5;
            --secondary-color: #166088;
            --accent-color: #20b2aa;
            --light-color: #f8f9fa;
            --dark-color: #333;
            --gray-color: #e9ecef;
            --success-color: #28a745;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        body {
            background-color: #f5f7fb;
            color: var(--dark-color);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 1.5rem 0;
            box-shadow: var(--shadow);
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo-icon {
            font-size: 2rem;
        }
        
        .tagline {
            font-size: 0.9rem;
            opacity: 0.9;
            margin-top: 5px;
        }
        
        /* Main Content */
        .main-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
            margin: 30px 0;
        }
        
        @media (min-width: 992px) {
            .main-content {
                grid-template-columns: 2fr 1fr;
            }
        }
        
        /* Compression Tool */
        .compression-tool {
            background: white;
            border-radius: 12px;
            padding: 30px;
            box-shadow: var(--shadow);
        }
        
        .tool-title {
            color: var(--secondary-color);
            margin-bottom: 25px;
            padding-bottom: 15px;
            border-bottom: 2px solid var(--gray-color);
        }
        
        /* Upload Area */
        .upload-area {
            border: 3px dashed var(--primary-color);
            border-radius: 10px;
            padding: 40px 20px;
            text-align: center;
            margin-bottom: 30px;
            background-color: rgba(74, 111, 165, 0.05);
            transition: all 0.3s ease;
            cursor: pointer;
        }
        
        .upload-area:hover {
            background-color: rgba(74, 111, 165, 0.1);
        }
        
        .upload-area.dragover {
            background-color: rgba(74, 111, 165, 0.2);
            border-color: var(--accent-color);
        }
        
        .upload-icon {
            font-size: 3.5rem;
            color: var(--primary-color);
            margin-bottom: 15px;
        }
        
        .upload-text h3 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }
        
        .upload-text p {
            color: #666;
            margin-bottom: 20px;
        }
        
        .upload-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }
        
        .upload-btn:hover {
            background-color: var(--secondary-color);
        }
        
        #fileInput {
            display: none;
        }
        
        /* Compression Controls */
        .compression-controls {
            margin-bottom: 30px;
        }
        
        .control-group {
            margin-bottom: 25px;
        }
        
        .control-label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--secondary-color);
        }
        
        .slider-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .quality-slider {
            flex-grow: 1;
            height: 8px;
            -webkit-appearance: none;
            appearance: none;
            background: var(--gray-color);
            border-radius: 4px;
            outline: none;
        }
        
        .quality-slider::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 22px;
            height: 22px;
            border-radius: 50%;
            background: var(--primary-color);
            cursor: pointer;
        }
        
        .quality-value {
            font-weight: 700;
            color: var(--primary-color);
            min-width: 40px;
            text-align: center;
        }
        
        .quality-labels {
            display: flex;
            justify-content: space-between;
            margin-top: 5px;
            font-size: 0.85rem;
            color: #777;
        }
        
        .format-select {
            width: 100%;
            padding: 12px;
            border: 2px solid var(--gray-color);
            border-radius: 8px;
            font-size: 1rem;
            color: var(--dark-color);
            background-color: white;
            cursor: pointer;
        }
        
        .format-select:focus {
            border-color: var(--primary-color);
            outline: none;
        }
        
        /* Action Buttons */
        .action-buttons {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .btn {
            padding: 14px 30px;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            flex: 1;
            min-width: 150px;
            text-align: center;
        }
        
        .btn-compress {
            background-color: var(--accent-color);
            color: white;
        }
        
        .btn-compress:hover {
            background-color: #1a9c95;
        }
        
        .btn-reset {
            background-color: var(--gray-color);
            color: var(--dark-color);
        }
        
        .btn-reset:hover {
            background-color: #d8dde3;
        }
        
        /* Results Section */
        .results-section {
            display: none;
            margin-top: 30px;
            padding-top: 25px;
            border-top: 2px solid var(--gray-color);
        }
        
        .results-title {
            color: var(--secondary-color);
            margin-bottom: 20px;
        }
        
        .image-comparison {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            margin-bottom: 25px;
        }
        
        @media (min-width: 768px) {
            .image-comparison {
                grid-template-columns: 1fr 1fr;
            }
        }
        
        .image-container {
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }
        
        .image-container img {
            width: 100%;
            height: auto;
            display: block;
        }
        
        .image-info {
            background-color: var(--light-color);
            padding: 15px;
            text-align: center;
        }
        
        .image-info h4 {
            margin-bottom: 10px;
            color: var(--secondary-color);
        }
        
        .stats {
            display: flex;
            justify-content: space-around;
            margin-top: 15px;
        }
        
        .stat {
            text-align: center;
        }
        
        .stat-value {
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--primary-color);
        }
        
        .stat-label {
            font-size: 0.85rem;
            color: #666;
        }
        
        .savings {
            background-color: rgba(40, 167, 69, 0.1);
            padding: 10px;
            border-radius: 8px;
            text-align: center;
            margin-top: 15px;
            font-weight: 600;
            color: var(--success-color);
        }
        
        .download-btn {
            background-color: var(--success-color);
            color: white;
            width: 100%;
            padding: 15px;
            margin-top: 20px;
        }
        
        .download-btn:hover {
            background-color: #218838;
        }
        
        /* Sidebar */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }
        
        /* Ad Spaces */
        .ad-space {  123
            background-color: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: var(--shadow);
            text-align: center;
            min-height: 280px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        
        .ad-label {
            font-size: 0.8rem;
            color: #999;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 15px;
        }
        
        .ad-placeholder {
            width: 100%;
            height: 250px;
            background-color: var(--gray-color);
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: #777;
            border: 2px dashed #ccc;
        }
        
        .ad-placeholder .ad-icon {
            font-size: 2.5rem;
            margin-bottom: 10px;
        }
        
        /* Instructions */
        .instructions {
            background-color: white;
            border-radius: 12px;
            padding: 25px;
            box-shadow: var(--shadow);
        }
        
        .instructions h3 {
            color: var(--secondary-color);
            margin-bottom: 15px;
        }
        
        .instructions ol {
            padding-left: 20px;
        }
        
        .instructions li {
            margin-bottom: 10px;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 40px 0 20px;
            margin-top: 50px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: 1fr;
            gap: 30px;
        }
        
        @media (min-width: 768px) {
            .footer-content {
                grid-template-columns: repeat(3, 1fr);
            }
        }
        
        .footer-section h3 {
            font-size: 1.2rem;
            margin-bottom: 20px;
            color: var(--accent-color);
        }
        
        .footer-section p, .footer-section a {
            color: #bbb;
            font-size: 0.95rem;
        }
        
        .footer-section a:hover {
            color: white;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            margin-top: 30px;
            border-top: 1px solid #444;
            color: #999;
            font-size: 0.9rem;
        }
        
        /* Loading */
        .loading {
            display: none;
            text-align: center;
            padding: 20px;
        }
        
        .spinner {
            width: 40px;
            height: 40px;
            border: 4px solid rgba(74, 111, 165, 0.2);
            border-top: 4px solid var(--primary-color);
            border-radius: 50%;
            animation: spin 1s linear infinite;
            margin: 0 auto 15px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <div class="logo">
                <div class="logo-icon">🖼️</div>
                <div>
                    <h1>ImageCompress Pro</h1>
                    <div class="tagline">Fast, secure, browser-based image optimization</div>
                </div>
            </div>
            <div class="header-ads">
                <!-- Ad Space 1 (Header) -->
                <div class="ad-space">
                    <div class="ad-label">Advertisement</div>
                    <div class="ad-placeholder">
                        <div class="ad-icon">📢</div>
                        <p>Google AdSense Ad</p>
                        <p>Ad Unit ID: ca-app-pub-8123763654650570/3031344597
                    </div>
                </div>
            </div>
        </div>
    </header>
    
    <div class="container">
        <div class="main-content">
            <!-- Main Compression Tool -->
            <div class="compression-tool">
                <h2 class="tool-title">Image Compression Tool</h2>
                
                <!-- Upload Area -->
                <div class="upload-area" id="uploadArea">
                    <div class="upload-icon">📁</div>
                    <div class="upload-text">
                        <h3>Drop your image here</h3>
                        <p>or click to browse (JPG, PNG, WebP supported)</p>
                        <button class="upload-btn" id="browseBtn">Browse Files</button>
                        <input type="file" id="fileInput" accept="image/*">
                    </div>
                </div>
                
                <!-- Selected File Info -->
                <div id="fileInfo" style="display: none; margin-bottom: 20px; padding: 15px; background-color: #e7f3ff; border-radius: 8px;">
                    <strong>Selected File:</strong> <span id="fileName"></span> (<span id="fileSize"></span>)
                </div>
                
                <!-- Compression Controls -->
                <div class="compression-controls">
                    <div class="control-group">
                        <label class="control-label">Compression Level (Quality)</label>
                        <div class="slider-container">
                            <input type="range" min="10" max="100" value="80" class="quality-slider" id="qualitySlider">
                            <span class="quality-value" id="qualityValue">80</span>
                        </div>
                        <div class="quality-labels">
                            <span>Smaller File</span>
                            <span>Better Quality</span>
                        </div>
                    </div>
                    
                    <div class="control-group">
                        <label class="control-label">Output Format</label>
                        <select class="format-select" id="formatSelect">
                            <option value="jpeg">JPEG (.jpg)</option>
                            <option value="png">PNG (.png)</option>
                            <option value="webp">WebP (.webp)</option>
                        </select>
                    </div>
                </div>
                
                <!-- Action Buttons -->
                <div class="action-buttons">
                    <button class="btn btn-compress" id="compressBtn">Compress Image</button>
                    <button class="btn btn-reset" id="resetBtn">Reset</button>
                </div>
                
                <!-- Loading Indicator -->
                <div class="loading" id="loadingIndicator">
                    <div class="spinner"></div>
                    <p>Compressing image...</p>
                </div>
                
                <!-- Results Section -->
                <div class="results-section" id="resultsSection">
                    <h3 class="results-title">Compression Results</h3>
                    
                    <div class="image-comparison">
                        <div class="image-container">
                            <img id="originalImage" alt="Original image">
                            <div class="image-info">
                                <h4>Original Image</h4>
                                <div class="stats">
                                    <div class="stat">
                                        <div class="stat-value" id="originalSize">0 KB</div>
                                        <div class="stat-label">Size</div>
                                    </div>
                                    <div class="stat">
                                        <div class="stat-value" id="originalDimensions">0x0</div>
                                        <div class="stat-label">Dimensions</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <div class="image-container">
                            <img id="compressedImage" alt="Compressed image">
                            <div class="image-info">
                                <h4>Compressed Image</h4>
                                <div class="stats">
                                    <div class="stat">
                                        <div class="stat-value" id="compressedSize">0 KB</div>
                                        <div class="stat-label">Size</div>
                                    </div>
                                    <div class="stat">
                                        <div class="stat-value" id="compressedDimensions">0x0</div>
                                        <div class="stat-label">Dimensions</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="savings" id="savingsInfo">
                        File size reduced by <span id="savingsPercent">0%</span> (<span id="savingsValue">0 KB</span> saved)
                    </div>
                    
                    <button class="btn download-btn" id="downloadBtn">Download Compressed Image</button>
                </div>
            </div>
            
            <!-- Sidebar -->
            <div class="sidebar">
                <!-- Ad Space 2 (Sidebar Top) -->
                <div class="ad-space">
                    <div class="ad-label">Advertisement</div>
                    <div class="ad-placeholder">
                        <div class="ad-icon">📈</div>
                        <p>Google AdSense Ad</p>
                        <p>Ad Unit ID:ca-app-pub-8123763654650570/3031344597
                    </div>
                </div>
                
                <!-- Instructions -->
                <div class="instructions">
                    <h3>How to Use</h3>
                    <ol>
                        <li>Select an image by clicking the upload area or dragging and dropping</li>
                        <li>Adjust the compression level using the slider</li>
                        <li>Choose your preferred output format</li>
                        <li>Click "Compress Image" to optimize your image</li>
                        <li>Download the compressed version</li>
                    </ol>
                    <p><strong>Note:</strong> All processing happens in your browser. Your images are never uploaded to any server.</p>
                </div>
                
                <!-- Ad Space 3 (Sidebar Bottom) -->
                <div class="ad-space">
                    <div class="ad-label">Advertisement</div>
                    <div class="ad-placeholder">
                        <div class="ad-icon">💰</div>
                        <p>Google AdSense Ad</p>
                        <p>Ad Unit ID:ca-app-pub-8123763654650570/3031344597
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>About ImageCompress Pro</h3>
                    <p>A free, browser-based image compression tool that helps reduce image file sizes without compromising quality. Perfect for web developers, photographers, and content creators.</p>
                </div>
                
                <div class="footer-section">
                    <h3>Features</h3>
                    <ul style="list-style: none;">
                        <li>✅ No image uploads - process locally</li>
                        <li>✅ Support for JPG, PNG, WebP</li>
                        <li>✅ Adjustable compression level</li>
                        <li>✅ Compare original vs compressed</li>
                        <li>✅ Responsive design</li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3>SEO Benefits</h3>
                    <p>Optimized images load faster, improving page load times and SEO rankings. Reduce bounce rates and improve user experience with properly compressed images.</p>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 ImageCompress Pro. All rights reserved. | This tool works entirely in your browser - no images are uploaded to any server.</p>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // DOM Elements
        const uploadArea = document.getElementById('uploadArea');
        const fileInput = document.getElementById('fileInput');
        const browseBtn = document.getElementById('browseBtn');
        const fileInfo = document.getElementById('fileInfo');
        const fileName = document.getElementById('fileName');
        const fileSize = document.getElementById('fileSize');
        const qualitySlider = document.getElementById('qualitySlider');
        const qualityValue = document.getElementById('qualityValue');
        const formatSelect = document.getElementById('formatSelect');
        const compressBtn = document.getElementById('compressBtn');
        const resetBtn = document.getElementById('resetBtn');
        const loadingIndicator = document.getElementById('loadingIndicator');
        const resultsSection = document.getElementById('resultsSection');
        const originalImage = document.getElementById('originalImage');
        const compressedImage = document.getElementById('compressedImage');
        const originalSize = document.getElementById('originalSize');
        const compressedSize = document.getElementById('compressedSize');
        const originalDimensions = document.getElementById('originalDimensions');
        const compressedDimensions = document.getElementById('compressedDimensions');
        const savingsInfo = document.getElementById('savingsInfo');
        const savingsPercent = document.getElementById('savingsPercent');
        const savingsValue = document.getElementById('savingsValue');
        const downloadBtn = document.getElementById('downloadBtn');
        
        // Variables
        let originalFile = null;
        let originalImageData = null;
        let compressedImageData = null;
        let compressedBlob = null;
        
        // Event Listeners
        browseBtn.addEventListener('click', () => fileInput.click());
        fileInput.addEventListener('change', handleFileSelect);
        uploadArea.addEventListener('dragover', handleDragOver);
        uploadArea.addEventListener('dragleave', handleDragLeave);
        uploadArea.addEventListener('drop', handleDrop);
        qualitySlider.addEventListener('input', updateQualityValue);
        compressBtn.addEventListener('click', compressImage);
        resetBtn.addEventListener('click', resetTool);
        downloadBtn.addEventListener('click', downloadCompressedImage);
        
        // Functions
        function handleFileSelect(e) {
            const file = e.target.files[0];
            processFile(file);
        }
        
        function handleDragOver(e) {
            e.preventDefault();
            uploadArea.classList.add('dragover');
        }
        
        function handleDragLeave(e) {
            e.preventDefault();
            uploadArea.classList.remove('dragover');
        }
        
        function handleDrop(e) {
            e.preventDefault();
            uploadArea.classList.remove('dragover');
            
            const file = e.dataTransfer.files[0];
            processFile(file);
        }
        
        function processFile(file) {
            if (!file || !file.type.match('image.*')) {
                alert('Please select a valid image file (JPG, PNG, WebP).');
                return;
            }
            
            originalFile = file;
            
            // Display file info
            fileName.textContent = file.name;
            fileSize.textContent = formatFileSize(file.size);
            fileInfo.style.display = 'block';
            
            // Load and display original image
            const reader = new FileReader();
            reader.onload = function(e) {
                originalImage.src = e.target.result;
                originalImageData = e.target.result;
                
                // Get image dimensions
                const img = new Image();
                img.onload = function() {
                    originalDimensions.textContent = `${img.width} × ${img.height}`;
                };
                img.src = e.target.result;
            };
            reader.readAsDataURL(file);
            
            // Reset results section
            resultsSection.style.display = 'none';
        }
        
        function updateQualityValue() {
            qualityValue.textContent = qualitySlider.value;
        }
        
        function compressImage() {
            if (!originalFile) {
                alert('Please select an image first.');
                return;
            }
            
            // Show loading indicator
            loadingIndicator.style.display = 'block';
            resultsSection.style.display = 'none';
            
            // Simulate compression delay for better UX
            setTimeout(performCompression, 500);
        }
        
        function performCompression() {
            const quality = parseInt(qualitySlider.value) / 100;
            const format = formatSelect.value;
            
            // Create a canvas element
            const canvas = document.createElement('canvas');
            const ctx = canvas.getContext('2d');
            
            // Load the image
            const img = new Image();
            img.onload = function() {
                // Set canvas dimensions to image dimensions
                canvas.width = img.width;
                canvas.height = img.height;
                
                // Draw image on canvas
                ctx.drawImage(img, 0, 0);
                
                // Get compressed data URL
                let mimeType;
                switch(format) {
                    case 'jpeg': mimeType = 'image/jpeg'; break;
                    case 'png': mimeType = 'image/png'; break;
                    case 'webp': mimeType = 'image/webp'; break;
                    default: mimeType = 'image/jpeg';
                }
                
                const compressedDataURL = canvas.toDataURL(mimeType, quality);
                compressedImage.src = compressedDataURL;
                compressedImageData = compressedDataURL;
                
                // Convert data URL to Blob to calculate size
                const byteString = atob(compressedDataURL.split(',')[1]);
                const mimeString = compressedDataURL.split(',')[0].split(':')[1].split(';')[0];
                const ab = new ArrayBuffer(byteString.length);
                const ia = new Uint8Array(ab);
                for (let i = 0; i < byteString.length; i++) {
                    ia[i] = byteString.charCodeAt(i);
                }
                compressedBlob = new Blob([ab], {type: mimeType});
                
                // Update UI with results
                updateResultsUI(img.width, img.height);
            };
            
            img.src = originalImageData;
        }
        
        function updateResultsUI(width, height) {
            // Hide loading indicator
            loadingIndicator.style.display = 'none';
            
            // Update size information
            originalSize.textContent = formatFileSize(originalFile.size);
            compressedSize.textContent = formatFileSize(compressedBlob.size);
            
            // Update dimensions
            originalDimensions.textContent = `${width} × ${height}`;
            compressedDimensions.textContent = `${width} × ${height}`;
            
            // Calculate and display savings
            const originalSizeBytes = originalFile.size;
            const compressedSizeBytes = compressedBlob.size;
            const savingsBytes = originalSizeBytes - compressedSizeBytes;
            const savingsPercentValue = ((savingsBytes / originalSizeBytes) * 100).toFixed(1);
            
            savingsPercent.textContent = `${savingsPercentValue}%`;
            savingsValue.textContent = formatFileSize(savingsBytes);
            
            // Show results section
            resultsSection.style.display = 'block';
            
            // Scroll to results
            resultsSection.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
        }
        
        function resetTool() {
            // Reset file input
            fileInput.value = '';
            originalFile = null;
            originalImageData = null;
            compressedImageData = null;
            compressedBlob = null;
            
            // Reset UI
            fileInfo.style.display = 'none';
            resultsSection.style.display = 'none';
            loadingIndicator.style.display = 'none';
            
            // Reset controls
            qualitySlider.value = 80;
            qualityValue.textContent = '80';
            formatSelect.value = 'jpeg';
            
            // Clear images
            originalImage.src = '';
            compressedImage.src = '';
        }
        
        function downloadCompressedImage() {
            if (!compressedBlob) {
                alert('No compressed image available. Please compress an image first.');
                return;
            }
            
            // Create download link
            const url = URL.createObjectURL(compressedBlob);
            const a = document.createElement('a');
            a.href = url;
            
            // Generate filename
            const originalName = originalFile.name;
            const extension = formatSelect.value === 'jpeg' ? 'jpg' : formatSelect.value;
            const compressedName = originalName.replace(/\.[^/.]+$/, "") + `-compressed.${extension}`;
            a.download = compressedName;
            
            // Trigger download
            document.body.appendChild(a);
            a.click();
            
            // Cleanup
            setTimeout(() => {
                document.body.removeChild(a);
                URL.revokeObjectURL(url);
            }, 100);
        }
        
        function formatFileSize(bytes) {
            if (bytes === 0) return '0 Bytes';
            
            const k = 1024;
            const sizes = ['Bytes', 'KB', 'MB', 'GB'];
            const i = Math.floor(Math.log(bytes) / Math.log(k));
            
            return parseFloat((bytes / Math.pow(k, i)).toFixed(2)) + ' ' + sizes[i];
        }
        
        // Initialize quality value display
        updateQualityValue();
    </script>
</body>
</html>
