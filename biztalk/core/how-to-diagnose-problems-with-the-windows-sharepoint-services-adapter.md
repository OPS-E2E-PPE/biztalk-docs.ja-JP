---
title: サービス アダプターを Windows SharePoint の問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c29569-3814-43a7-93f8-a39c3464a831
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5451a4fffd4c75b52f46741b1e7228dacf9f6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385211"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターに関する問題を診断する方法
このセクションには、Windows Sharepoint Services アダプターに関する問題の診断に役立つことができますの手順が含まれています。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>IIS および HTTPERR ログ ファイルの IIS サーバーのエラーを確認してください。  
  
- ソースまたはターゲット IIS サーバーのログ ファイルは、Windows Sharepoint Services アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
- 既定では、HTTPERR ログ ファイル、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ベースのコンピューターは、次のディレクトリに配置されます。  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルが収録のみ[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Windows SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)