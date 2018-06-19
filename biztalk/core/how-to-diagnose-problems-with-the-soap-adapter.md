---
title: SOAP アダプターに関する問題を診断する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16c93333-cb32-49bc-a1c4-9d726ab41850
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db1d495eb301f93100a6ac9a4e50c8f1c57e5f5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249474"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>SOAP アダプターに関する問題を診断する方法
ここでは、SOAP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>IIS サーバーの IIS ログおよび HTTPERR ログでエラーの有無を確認する  
  
-   ソースまたはターゲットの IIS サーバー ログ ファイルには、SOAP アダプターに関する問題のトラブルシューティングに役立つ情報が含まれています。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
     既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\HTTPERR\  
  
    > [!NOTE]
    >  HTTPERR ログ ファイルが上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SOAP アダプターのトラブルシューティング](../core/troubleshooting-the-soap-adapter.md)