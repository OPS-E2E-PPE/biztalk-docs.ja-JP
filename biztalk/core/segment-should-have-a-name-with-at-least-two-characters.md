---
title: セグメントは、少なくとも 2 つの文字の名前が必要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f80bbc4a-151a-4094-8640-1944e8812730
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 814da0db8dce26e9078126ede767f623b59b6401
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251012"
---
# <a name="segment-should-have-a-name-with-at-least-two-characters"></a>セグメントは、少なくとも 2 つの文字の名前が必要
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                             SchemaCode103EInvalidTagLength                             |
|  メッセージ テキスト   |                 セグメントは少なくとも 2 つの文字の名前である必要があります。                  |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のセグメントの名前に、少なくとも 2 つの文字があるないためにで受信インターチェンジでした、受信パイプラインによって処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジ内の各セグメントの名前に、少なくとも 2 つの文字があることを確認してもらい、インターチェンジのインターチェンジの送信者を依頼します。