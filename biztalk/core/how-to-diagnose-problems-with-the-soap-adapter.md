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
ms.openlocfilehash: 93b0339f44827dd716afc517ed3aeb8aca9c25e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385241"
---
# <a name="how-to-diagnose-problems-with-the-soap-adapter"></a>SOAP アダプターに関する問題を診断する方法
このセクションには、SOAP アダプターに関する問題の診断に役立つことができますの手順が含まれています。  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a>IIS ログと IIS サーバーのエラーの HTTPERR ログを確認してください。  
  
- ソースまたはターゲット IIS サーバーのログ ファイルは、SOAP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] コンピューターの IIS ログ ファイルは次のディレクトリにあります。  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* IIS サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
   既定では、HTTPERR ログ ファイル、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]ベースのコンピューターは、次のディレクトリに配置されます。  
  
   <em>%WinDir%\\</em>system32\LogFiles\HTTPERR\  
  
  > [!NOTE]
  >  HTTPERR ログ ファイルは上でのみ使用可能な[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SOAP アダプターのトラブルシューティング](../core/troubleshooting-the-soap-adapter.md)