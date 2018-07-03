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
ms.openlocfilehash: 8966e3d95e89aff023300a9834ab1bca2915421f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994851"
---
# <a name="receipt-delivery-option-value-is-invalid"></a>Receipt-Delivery-Option の値が無効です
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
 このエラー/警告/情報イベントは、受信した AS2 メッセージの Receipt-Delivery-Option が有効な URL ではなく、AS2 RFC 4130 の仕様に準拠していないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 メッセージの Receipt-Delivery-Option を有効な URL を含むように変更し、AS2 RFC 4130 のセクション 7.3 の仕様に準拠するようにしてから、AS2 メッセージを再送信します。