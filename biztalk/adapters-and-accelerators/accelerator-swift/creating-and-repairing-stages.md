---
title: 作成と修復段階 |Microsoft ドキュメント
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
ms.openlocfilehash: bb87112775b9664badf319796e1a6243cf6eb082
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208810"
---
# <a name="creating-and-repairing-stages"></a>作成とステージの修復
任意のワークフローの最初のステージは、Create または修復の段階、として定義されている機能を持つロールの作成は、または修復します。 失敗したメッセージとして BizTalk メッセージ ボックスから、メッセージの生成元または[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが経由でメッセージを手動で作成、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。  
  
 メッセージの最初のデジタル署名者は、元のメッセージの作成者または修理会社に自分のデジタル署名を追加、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]作成またはメッセージを修復した後のフォームです。 この最初の署名は、メッセージの作成者または修理会社の身元を証明だけでなく、また現在の状態でメッセージの内容をロックします。 メッセージは、最初の署名後に変更する場合、デジタル署名スタックが壊れていると、フォーム上のデジタル署名が無効であることを示すユーザーに警告が表示されます。