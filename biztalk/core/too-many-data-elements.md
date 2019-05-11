---
title: データ要素が多すぎる |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5000577d-5748-4e81-a394-86b2a780d70f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cb05cc31331dcc2633b7dc398c8f77a369c3f28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395422"
---
# <a name="too-many-data-elements"></a>データ要素が多すぎます
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                          X12DeTooManyDataElementsDescription                           |
|  メッセージ テキスト   |                                 データ要素が多すぎます                                 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジ内のセグメントにドキュメント スキーマまたはサービス スキーマで許容されているよりも多くのデータ要素が含まれていたため、受信パイプラインで受信インターチェンジを処理できなかったか、送信パイプラインで送信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、要求されている数のデータ要素がセグメントに含まれていることを確認するようインターチェンジの送信者に依頼し、必要に応じてセグメントから余分なデータ要素を削除して、セグメントがスキーマに準拠するようにしてもらいます。