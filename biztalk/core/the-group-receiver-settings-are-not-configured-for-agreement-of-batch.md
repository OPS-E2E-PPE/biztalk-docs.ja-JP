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
ms.openlocfilehash: aa5b6e201ffc3321920e23129adf9073589c25f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394126"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a>グループの受信者設定がバッチのアグリーメント構成されていません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                     |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                          |
| 製品バージョン |                                     [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                      |
|    イベント ID     |                                                                  -                                                                  |
|  イベント ソース   |                       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                        |
|    コンポーネント    |                                                           バッチ処理エンジン                                                           |
|  シンボル名  |                                                      GroupReceiverNotSelected                                                       |
|  メッセージ テキスト   | グループの受信者設定がバッチのアグリーメント構成されていない{0}します。 これは、バッチ処理を続行する前に構成する必要があります。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、2 つの条件のいずれかが発生したことを示します。  
  
-   バッチ処理オーケストレーションは、エンコードの構文を含む UNB1.1 フィールド (EDIFACT でエンコードされたインターチェンジ) に対してが設定されていないため、受信したバッチ要素を検証できませんでした。  
  
-   ヘッダーのプロパティが完了しなかったために、バッチ処理オーケストレーションは、バッチ要素のエンベロープ設定を作成できませんでした (x12 ISA、GS、および ST プロパティ インターチェンジまたは EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティ)。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   バッチ処理オーケストレーションは、エンコードの構文が設定されていないため、受信したバッチ要素を検証できませんだった場合、は、EDI のプロパティ ダイアログ ボックスの UNB セグメントの定義 ページで、UNB1.1 フィールドのエンコードの構文を設定します。  
  
-   場合は、バッチ処理オーケストレーションは、ヘッダーのプロパティが完了しなかったために、バッチ要素のエンベロープ設定を作成できませんでした、確認のインターチェンジが x12 ISA、GS、および ST プロパティ セットまたは UNA、UNB、UNG、および UNH プロパティをEDIFACT インターチェンジが設定されます。