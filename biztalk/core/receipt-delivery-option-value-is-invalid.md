---
title: Receipt-delivery-option の値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eed306b-0912-4694-a55c-976128117c02
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f69a1f396b6b788f3aee446b5feb501eb2f59e4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398232"
---
# <a name="receipt-delivery-option-value-is-invalid"></a>Receipt-delivery-option の値が無効です。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       AS2 エンジン                                       |
|  シンボル名  |                           InvalidReceiptDeliveryOptionError                            |
|  メッセージ テキスト   |                 Receipt-delivery-option の値:"{0}"が無効です。  {1}                  |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントはの Receipt-delivery-option で受信した AS2 メッセージが有効な URL ではありませんが、AS2 RFC 4130 の仕様に準拠していないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、AS2 メッセージの有効な URL を含めると、AS2 RFC 4130 のセクション 7.3 の仕様に準拠しているし、AS2 メッセージ再送信する変更に確認メッセージの配信オプションがあります。