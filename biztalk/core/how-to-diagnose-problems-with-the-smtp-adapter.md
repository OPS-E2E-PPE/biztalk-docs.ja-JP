---
title: SMTP アダプターに関する問題を診断する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a41a347534c07b522de5fc073933758870bf8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249674"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a>SMTP アダプターに関する問題の診断方法
ここでは SMTP アダプターに関する問題の診断手順について説明します。  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a>SMTP サーバーの SMTP ログ ファイルでエラーの有無を確認する  
  
-   ターゲットの SMTP サーバーのログ ファイルには、SMTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] の SMTP ログ ファイルは次のディレクトリにあります。  
  
     *%Windir%\\*system32\LogFiles\SMTPSVC1\  
  
    > [!NOTE]
    >  *%Windir%* SMTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  
    > [!NOTE]
    >  既定では、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の SMTP ロギングは無効になっています。 SMTP ロギングを有効にする方法の詳細については、Windows Server のドキュメントを参照してください。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SMTP アダプターのトラブルシューティング](../core/troubleshooting-the-smtp-adapter.md)