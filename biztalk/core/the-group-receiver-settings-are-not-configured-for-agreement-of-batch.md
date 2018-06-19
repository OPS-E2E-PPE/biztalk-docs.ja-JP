---
title: バッチのアグリーメントのグループの受信者設定が構成されていません |Microsoft ドキュメント
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
ms.openlocfilehash: 8ea41ad5c8de88e446a86745b57ff282d5b90af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279074"
---
# <a name="the-group-receiver-settings-are-not-configured-for-agreement-of-batch"></a>バッチのアグリーメントにグループの受信者設定が構成されていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|GroupReceiverNotSelected|  
|メッセージ テキスト|バッチ {0} のアグリーメントは、グループの受信者設定は構成されていません。 バッチ処理を続行する前にこの設定を構成する必要があります。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、2 つの状態のいずれか 1 つが発生したことを示します。  
  
-   エンコードの構文を含む UNB1.1 フィールド (EDIFACT でエンコードされたインターチェンジの場合) が設定されていなかったため、バッチ処理オーケストレーションで受信したバッチ要素を検証できませんでした。  
  
-   ヘッダー プロパティ (X12 インターチェンジの ISA、GS、および ST プロパティ、または EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティ) が完全でなかったため、バッチ処理オーケストレーションでバッチ要素のエンベロープ設定を作成できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   エンコードの構文が設定されていないためにバッチ処理オーケストレーションで受信したバッチ要素を検証できなかった場合は、[EDI のプロパティ] ダイアログ ボックスの [UNB セグメントの定義] ページにある UNB1.1 フィールドにエンコードの構文を設定します。  
  
-   ヘッダー プロパティが完全でなかったためにバッチ処理オーケストレーションでバッチ要素のエンベロープ設定を作成できなかった場合は、X12 インターチェンジの ISA、GS、および ST プロパティが設定されていること、または EDIFACT インターチェンジの UNA、UNB、UNG、および UNH プロパティが設定されていることを確認します。