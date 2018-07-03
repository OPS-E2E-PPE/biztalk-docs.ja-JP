---
title: BizTalk メッセージ本文の要素が指定されていない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af5d63c0-af96-4e34-828f-d29638cdf46d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 206cbea171b3453fed7e7db7d5c67d658fcccc10
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994547"
---
# <a name="biztalk-message-body-element-not-specified"></a>BizTalk メッセージ本文要素が指定されていません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                     BizTalk メッセージ本文要素が指定されていません                     |
  
## <a name="explanation"></a>説明  
 このエラーは、送信 WCF メッセージにテンプレート オプションが使用されていることを示します。 一方で、テンプレート式には BizTalk メッセージ本文要素が含まれません。  
  
## <a name="user-action"></a>ユーザーの操作  
 テンプレート式に次の要素が含まれていることを確認: \< **bts メッセージの本文の xmlns ="<http://www.microsoft.com/schemas/bts2007>"encoding ="[xml&#124;base64&#124;16 進&#124;文字列]"/**\>します。