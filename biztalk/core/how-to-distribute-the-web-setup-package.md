---
title: Web セットアップ パッケージを配布する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, distributing
- Web services, deploying
ms.assetid: 0db71fdf-80d9-4ad5-b0d4-730d0bb549d4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecffab64a02a8c42f7a50f2c87629aa1bf520662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385173"
---
# <a name="how-to-distribute-the-web-setup-package"></a>Web セットアップ パッケージを配布する方法
インストール パッケージを作成した後、Web サービスをセットアップするために MSI ファイルと BindingInfo.xml ファイルがコピーされる配布フォルダを作成する必要があります。  
  
### <a name="to-distribute-the-web-setup-package"></a>Web セットアップ パッケージを配布するには  
  
1.  セットアップ ファイルを格納する配布フォルダを作成します。  
  
2.  Web セットアップ プロジェクト出力フォルダから配布フォルダに .MSI ファイルをコピーします。  
  
3.  ASP.NET Web サービス プロジェクト フォルダの temp フォルダから配布フォルダに BindingInfo.xml ファイルをコピーします。  
  
## <a name="see-also"></a>参照  
 [Visual Studio がインストールされていないコンピューターへの公開済み Web サービスの展開](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)