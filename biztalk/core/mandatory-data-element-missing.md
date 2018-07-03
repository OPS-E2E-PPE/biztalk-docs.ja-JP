---
title: 必須データ要素がありません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510d54b3-13de-4735-92ec-04fd4b9d460e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a44e4824805a137121bf1f5bd030cb16329484d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966491"
---
# <a name="mandatory-data-element-missing"></a>必須のデータ要素がありません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                      X12DeMandatoryDataElementMissingDescription                       |
|  メッセージ テキスト   |                             必須のデータ要素がありません                             |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージ スキーマで要求されている (minOccurs が 0 より大きい) データ要素がインターチェンジに含まれていなかったため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージ スキーマで要求されているすべてのデータ要素がインターチェンジに含まれていることを確認し、メッセージを再送信してもらいます。