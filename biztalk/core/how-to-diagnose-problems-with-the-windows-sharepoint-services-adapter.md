---
title: サービスのアダプターを Windows SharePoint の問題を診断する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 67aa43628e8db4384a411fd1cc4696b7955b3752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249002"
---
# <a name="how-to-diagnose-problems-with-the-windows-sharepoint-services-adapter"></a>Windows SharePoint Services アダプターに関する問題を診断する方法
このセクションでは、Windows Sharepoint Services アダプターに関する問題の診断に使用できる手順について説明します。  
  
### <a name="check-the-iis-and-httperr-log-files-of-the-iis-server-for-errors"></a>IIS サーバーの IIS ログ ファイルと TTPERR ログ ファイルでエラーを確認する  
  
-   ソースまたはターゲットの IIS サーバー ログ ファイルには、Windows Sharepoint Services アダプターに関する問題のトラブルシューティングに役立つ情報が含まれている場合があります。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
-   既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  HTTPERR ログ ファイルは、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] コンピューターでのみ使用できます。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [Windows SharePoint Services アダプターのトラブルシューティング](../core/troubleshooting-the-windows-sharepoint-services-adapter.md)