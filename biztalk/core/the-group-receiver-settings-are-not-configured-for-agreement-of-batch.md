---
title: グループの受信者設定がバッチのアグリーメント構成されていません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57b205e9-aaab-43d1-b373-17d206957814
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 534d426d192e27bbe7c6c7e866399b42360a8e3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990643"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a>バッチのアグリーメントにグループの受信者設定が構成されていません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| 製品バージョン |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    イベント ID     |                                                                  -                                                                  |
|  イベント ソース   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                        |
|    コンポーネント    |                                                           バッチ処理エンジン                                                           |
|  シンボル名  |                                                      GroupReceiverNotSelected                                                       |
|  メッセージ テキスト   | グループの受信者設定がバッチのアグリーメント構成されていない{0}します。 バッチ処理を続行する前にこの設定を構成する必要があります。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、2 つの状態のいずれか 1 つが発生したことを示します。  
  
-   エンコードの構文を含む UNB1.1 フィールド (EDIFACT でエンコードされたインターチェンジの場合) が設定されていなかったため、バッチ処理オーケストレーションで受信したバッチ要素を検証できませんでした。  
  
-   ヘッダー プロパティ (X12 インターチェンジの ISA、GS、および ST プロパティ、または EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティ) が完全でなかったため、バッチ処理オーケストレーションでバッチ要素のエンベロープ設定を作成できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   エンコードの構文が設定されていないためにバッチ処理オーケストレーションで受信したバッチ要素を検証できなかった場合は、[EDI のプロパティ] ダイアログ ボックスの [UNB セグメントの定義] ページにある UNB1.1 フィールドにエンコードの構文を設定します。  
  
-   ヘッダー プロパティが完全でなかったためにバッチ処理オーケストレーションでバッチ要素のエンベロープ設定を作成できなかった場合は、X12 インターチェンジの ISA、GS、および ST プロパティが設定されていること、または EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティが設定されていることを確認します。