---
title: SMTP アダプターに関する問題を診断する方法 |Microsoft Docs
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
ms.openlocfilehash: cd84acb26dfc70f5f2d84e93bb700ab48ea2fa03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338329"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a>SMTP アダプターに関する問題の診断方法
このセクションには、SMTP アダプターに関する問題の診断に役立つことができますの手順が含まれています。  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a>SMTP サーバーの SMTP ログ ファイルにエラーを確認してください。  
  
- ターゲットの SMTP サーバーのログ ファイルは、SMTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。 既定では、SMTP ログ ファイル[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]次のディレクトリにあります。  
  
   <em>%WinDir%\\</em>system32\LogFiles\SMTPSVC1\  
  
  > [!NOTE]
  >  *%Windir%* SMTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。  
  > 
  > [!NOTE]
  >  既定の SMTP ログ記録が無効に[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]します。 SMTP のログ記録を有効にする方法については、Windows Server のマニュアルを参照してください。  
  
## <a name="see-also"></a>参照  
 [トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md)   
 [SMTP アダプターのトラブルシューティング](../core/troubleshooting-the-smtp-adapter.md)