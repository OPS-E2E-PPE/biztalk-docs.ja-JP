---
title: SOAP アダプターに関する問題を診断する方法 |Microsoft Docs
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
ms.openlocfilehash: 85c585c3fae6c6f49412f00e02276276e9c73b64
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968315"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>SOAP アダプターに関する問題を診断する方法
ここでは、SOAP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>IIS サーバーの IIS ログおよび HTTPERR ログでエラーの有無を確認する  
  
- ソースまたはターゲットの IIS サーバー ログ ファイルには、SOAP アダプターに関する問題のトラブルシューティングに役立つ情報が含まれています。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
   既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] ベースのコンピューターの HTTPERR ログ ファイルは次のディレクトリにあります。  
  
   <em>%Windir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SOAP アダプターのトラブルシューティング](../core/troubleshooting-the-soap-adapter.md)