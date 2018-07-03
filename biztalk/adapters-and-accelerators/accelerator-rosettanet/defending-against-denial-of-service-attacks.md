---
title: サービス拒否攻撃に対する防御 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab2aa48e126aafc7b2202547fd72806b5d471ef4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976939"
---
# <a name="defending-against-denial-of-service-attacks"></a>サービス拒否攻撃から保護
サービス拒否攻撃は Microsoft® のインストールを開始ユーザーでした[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]によって生じて、RNIFReceive.aspx ページが表示されます。 そのページに多数の空のメッセージを送信する場合があります。 このような攻撃を放置すると、ASPX 受信ページで発行されたイベントがイベント ログに収まりきらなくなる場合があります。  
  
## <a name="defending-against-an-attack"></a>攻撃からの保護  
 サービス拒否攻撃からサーバーを守るには、イベント ログを適度なサイズに維持し、また大量のイベント数を処理する手段をとることをお勧めします。 たとえば、最大ログ サイズを設定する、イベントの上書きが可能な手段をとる、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) を使用してログのサイズを管理するなどの方法があります。 詳細については、Microsoft のヘルプを参照してください。 [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™ します。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、セキュリティの管理](manage-configuration-certificates-databases-security.md)