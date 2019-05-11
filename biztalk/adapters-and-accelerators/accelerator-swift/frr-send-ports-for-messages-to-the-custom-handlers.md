---
title: カスタム ハンドラーへのメッセージの FRR 送信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- custom handlers
- FRR, custom handlers
- send ports, FRR
- send ports, custom handlers
ms.assetid: 486d7410-fde1-4a9b-a9c2-64c1ed85ebc0
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1d4eed6f26e0636d77b39c7294ec2b52357ae48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377797"
---
# <a name="frr-send-ports-for-messages-to-the-custom-handlers"></a>カスタム ハンドラーへのメッセージの FRR 送信ポート
FRR でカスタム ハンドラーを有効にする、FRR 送信ポートの一連のカスタム ハンドラーへの特定の種類の元のメッセージのコピーのルーティングを作成する必要があります。 これらの送信ポートには次のパイプライン コンポーネントが必要です。  

- アセンブル ステージで SWIFT アセンブラー  

- エンコード段階で SWIFTSendFrrComponent パイプライン コンポーネント  

  カテゴリ 0 ~ 9 の SWIFT FIN メッセージが正常に送信されませんを除くすべてのメッセージ、送信ポートは、次のフィルターが必要です。  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceType == [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  

- BTS します。操作は、メッセージの種類ごとに必要な値に設定します。 BTS の考えられる値。Operation プロパティでは、表を参照して[カスタム ハンドラーへの送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。  

  正常に送信されないカテゴリ 0 ~ 9 の SWIFT FIN メッセージ、送信ポートは、次のフィルターが必要です。  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SendingServiceTyp==[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrFailed true = =  

- BTS します。操作 = =[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendMTMsg  

- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason は、メッセージの種類ごとに必要な値に設定します。 BTS の考えられる値。Operation プロパティでは、表を参照して[カスタム ハンドラーへの送信用として FRR 送信ポートを作成する](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)します。
