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
# <a name="how-to-distribute-the-web-setup-package"></a>Web セットアップ パッケージを配布する方法
インストール パッケージを作成した後、Web サービスをセットアップするために MSI ファイルと BindingInfo.xml ファイルがコピーされる配布フォルダを作成する必要があります。  
  
### <a name="to-distribute-the-web-setup-package"></a>Web セットアップ パッケージを配布するには  
  
1.  セットアップ ファイルを格納する配布フォルダを作成します。  
  
2.  Web セットアップ プロジェクト出力フォルダから配布フォルダに .MSI ファイルをコピーします。  
  
3.  ASP.NET Web サービス プロジェクト フォルダの temp フォルダから配布フォルダに BindingInfo.xml ファイルをコピーします。  
  
## <a name="see-also"></a>参照  
 [非 Visual Studio コンピューターに公開された Web サービスを展開します。](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)