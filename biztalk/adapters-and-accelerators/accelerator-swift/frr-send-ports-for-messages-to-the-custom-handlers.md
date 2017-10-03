---
title: "カスタム ハンドラーへのメッセージの送信ポートを FRR |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6babc312ddad7d77a96e29bc9e59ec9298aa6ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a>カスタム ハンドラーへのメッセージの送信ポートを FRR
FRR でカスタム ハンドラーを有効にするのには、特定の型の元のメッセージのコピーをカスタム ハンドラーにルーティングする一連の FRR 送信ポートを作成する必要があります。 これらの送信ポートには次のパイプライン コンポーネントが必要です。  
  
-   アセンブル ステージに SWIFT アセンブラー  
  
-   エンコード ステージに SWIFTSendFrrComponent パイプライン コンポーネント  
  
 カテゴリ、0 ~ 9 SWIFT FIN メッセージが正常に送信されないことを除き、すべてのメッセージの送信ポートは、次のフィルターが必要です。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType = = [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   BTS です。操作は、メッセージの種類ごとに必要な値に設定します。 BTS の考えられる値です。操作のプロパティ内のテーブルを参照してください[FRR 送信ポートを作成するカスタム ハンドラーに送信の](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。  
  
 正常に送信されていないカテゴリ、0 ~ 9 SWIFT FIN メッセージ、送信ポートは、次のフィルターが必要です。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceTyp = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrFailed = = true  
  
-   BTS です。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason は、メッセージの種類ごとに必要な値に設定します。 BTS の考えられる値です。操作のプロパティ内のテーブルを参照してください[FRR 送信ポートを作成するカスタム ハンドラーに送信の](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。