---
title: 作成とステージの修復 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- stages, repair
- stages, create
ms.assetid: 07d7ce7b-ed15-40a7-9c85-280a1d38985b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9f26752fce0da2290892a46c051652001493bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378440"
---
# <a name="creating-and-repairing-stages"></a>作成と修復段階
作成または修復のステージは、任意のワークフローの最初のステージ、として定義されている機能を持つロールの作成、または修復します。 失敗したメッセージとして BizTalk メッセージ ボックスから、メッセージの生成元または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが経由でメッセージを手動で作成、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
 メッセージの最初のデジタル署名者は、元のメッセージの作成者または修理会社に自分のデジタル署名を追加、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作成またはメッセージを修復した後のフォームです。 この最初の署名は、メッセージの作成者または修理会社の身元を証明だけでなく、また現在の状態でメッセージの内容をロックします。 最初のサインインした後、メッセージが変更される場合、デジタル署名のスタックが壊れていると、フォーム上のデジタル署名が有効であることを通知する警告が表示されます。