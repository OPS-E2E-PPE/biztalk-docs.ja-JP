---
title: "サービス拒否攻撃から保護 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 667b9d321f7703f770297b001ef2a99be2bf4902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="defending-against-denial-of-service-attacks"></a>サービス拒否攻撃から保護
他のユーザーのインストールに対するサービス拒否攻撃を開始できませんでした[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]によって生じて、RNIFReceive.aspx ページが表示されます。 そのページに多数の空のメッセージを送信するときは可能性があります。 このような攻撃を放置すると、ASPX 受信ページで発行されたイベントがイベント ログに収まりきらなくなる場合があります。  
  
## <a name="defending-against-an-attack"></a>攻撃からの保護  
 サービス拒否攻撃からサーバーを守るには、イベント ログを適度なサイズに維持し、また大量のイベント数を処理する手段をとることをお勧めします。 たとえば、最大ログ サイズを設定する、イベントの上書きが可能な手段をとる、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) を使用してログのサイズを管理するなどの方法があります。 詳細については、ヘルプを参照して[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™ します。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)