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
ms.openlocfilehash: f0dc316f039e56271f4d5540e3853aa82287b20d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283995"
---
# <a name="defending-against-denial-of-service-attacks"></a>サービス拒否攻撃から保護
サービス拒否攻撃は Microsoft® のインストールを開始ユーザーでした[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]によって生じて、RNIFReceive.aspx ページが表示されます。 そのページに多数の空のメッセージを送信する場合があります。 場合はオフの場合、このような攻撃は、ASPX によって発行されたイベントをイベント ログをあふれでした左には、ページが表示されます。  
  
## <a name="defending-against-an-attack"></a>攻撃からの保護  
 サーバーに対するサービス拒否攻撃を防御するために、適切なサイズのイベント ログを維持し、過度のイベントを処理する手順を実行することをお勧めします。 これには、最大ログ サイズを設定して、イベントを上書きするかを使用する方法を選択する[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® ログのサイズを管理する Management Instrumentation (WMI)。 詳細については、Microsoft のヘルプを参照してください。 [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™ します。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、セキュリティの管理](manage-configuration-certificates-databases-security.md)