---
title: 受信アダプターの操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b61ea356-f2a1-4604-8e52-13d2961399d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d4e5ee9d9afbbb687f415b42652d76a50bac4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980123"
---
# <a name="receive-adapter-operations"></a>受信アダプターの操作
受信アダプターでは次の操作を実行できます。  

- **一方向の送信: void SubmitMessage (IBaseMessage msg)。** 受信ポートからメッセージを受信した後、アダプターに送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サブスクライブを行うオーケストレーションで処理または送信ポートにします。  

- **中断: は void MoveToSuspendQ (IBaseMessage msg) です。** 解析エラー、送信エラー、シリアル化エラーなどが送信後に発生したと判断した場合、受信アダプターは、メッセージを保留キューに移動します。  

- **要求を送信: void SubmitRequestMessage (IBaseMessage requestMsg、文字列 correlationToken、[MarshalAs(UnmanagedType.Bool)] bool firstResponseOnly、DateTime expirationTime、IBTTransmitter responseCallback)。** 受信アダプターの送信、受信メッセージを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求-応答の組み合わせ。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、この要求メッセージを適切に処理した後、応答を受信アダプターに送信します。この応答は、受信アダプターから特定のエンドポイントに転送されます。
