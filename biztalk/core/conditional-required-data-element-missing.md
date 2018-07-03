---
title: 条件付きの必須データ要素がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5105c03-fa26-4c38-a276-c656f3076d5f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f43ebf2ba593ad5133b93400bf0e9cb1151dc45b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978443"
---
# <a name="conditional-required-data-element-missing"></a>必須の条件付きデータ要素がありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                 X12DeConditionalRequiredDataElementMissingDescription                  |
|  メッセージ テキスト   |                       必須の条件付きデータ要素がありません                        |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12ConditionDesignatorX ルールで必要になるデータ要素がインターチェンジに存在していないため、EDI 受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーは、BizTalk Server の構成や操作ではなく、受信インターチェンジの問題である可能性があります。 このエラーを解決するには、インターチェンジの送信者に連絡し、インターチェンジに使用されている文字または UNB1.1 フィールドで識別されている文字セットのどちらかを変更し、それらを一致させる必要があることを伝えます。