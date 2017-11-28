---
title: "Web セットアップ パッケージを配布する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, distributing
- Web services, deploying
ms.assetid: 0db71fdf-80d9-4ad5-b0d4-730d0bb549d4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed7e6277045593360cbdfe57848f7313054b60f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-distribute-the-web-setup-package"></a><span data-ttu-id="cbc57-102">Web セットアップ パッケージを配布する方法</span><span class="sxs-lookup"><span data-stu-id="cbc57-102">How to Distribute the Web Setup Package</span></span>
<span data-ttu-id="cbc57-103">インストール パッケージを作成した後、Web サービスをセットアップするために MSI ファイルと BindingInfo.xml ファイルがコピーされる配布フォルダを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbc57-103">After you create the installation package, you need to create a distribution folder where a MSI file and a BindingInfo.xml file are copied to set up the Web service.</span></span>  
  
### <a name="to-distribute-the-web-setup-package"></a><span data-ttu-id="cbc57-104">Web セットアップ パッケージを配布するには</span><span class="sxs-lookup"><span data-stu-id="cbc57-104">To distribute the Web setup package</span></span>  
  
1.  <span data-ttu-id="cbc57-105">セットアップ ファイルを格納する配布フォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="cbc57-105">Create a distribution folder to contain your setup files.</span></span>  
  
2.  <span data-ttu-id="cbc57-106">Web セットアップ プロジェクト出力フォルダから配布フォルダに .MSI ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="cbc57-106">Copy the .MSI file from the Web Setup project output folder to the distribution folder.</span></span>  
  
3.  <span data-ttu-id="cbc57-107">ASP.NET Web サービス プロジェクト フォルダの temp フォルダから配布フォルダに BindingInfo.xml ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="cbc57-107">Copy the BindingInfo.xml file from the temp folder in the ASP.NET Web Service project folder to the distribution folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc57-108">参照</span><span class="sxs-lookup"><span data-stu-id="cbc57-108">See Also</span></span>  
 [<span data-ttu-id="cbc57-109">非 Visual Studio コンピューターに公開された Web サービスを展開します。</span><span class="sxs-lookup"><span data-stu-id="cbc57-109">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)