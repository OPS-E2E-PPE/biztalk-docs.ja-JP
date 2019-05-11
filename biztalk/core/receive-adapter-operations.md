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
ms.openlocfilehash: 865ad83aa9dc7e19b87f193326dd9061736c2fc0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398264"
---
# <a name="receive-adapter-operations"></a>受信アダプターの操作
受信アダプターは、次の操作を実行できます。  

- **一方向の送信: void SubmitMessage (IBaseMessage msg)。** 受信ポートからメッセージを受信した後、アダプターに送信する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サブスクライブを行うオーケストレーションで処理または送信ポートにします。  

- **中断: は void MoveToSuspendQ (IBaseMessage msg) です。** アダプターは、ユーザーが解析、送信後、転送、シリアル化、またはその他の該当するエラーが発生しましたが判断した場合、メッセージを保留キューに移動します。  

- **要求を送信: void SubmitRequestMessage (IBaseMessage requestMsg、文字列 correlationToken、[MarshalAs(UnmanagedType.Bool)] bool firstResponseOnly、DateTime expirationTime、IBTTransmitter responseCallback)。** 受信アダプターの送信、受信メッセージを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求-応答の組み合わせ。 後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この要求メッセージを適切に処理する特定のエンドポイントに送信アダプターに応答を送信します。
