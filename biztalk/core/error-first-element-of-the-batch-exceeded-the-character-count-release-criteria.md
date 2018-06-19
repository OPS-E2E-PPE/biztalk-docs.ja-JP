---
title: バッチの最初の要素を文字数のリリース条件セットを超えています |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4b06f8f-247d-4e93-8c4e-5e86e4ad70c9
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 746fbfabb2fe411310735f66c6d8a8398a94a5dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241554"
---
# <a name="the-first-element-of-the-batch-exceeded-the-character-count-release-criteria-set"></a>バッチの最初の要素が、文字数のリリース条件セットで指定されている文字数を超えました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|バッチ処理エンジン|  
|シンボル名|FirstElementExceededCharCount|  
|メッセージ テキスト|バッチの最初の要素が、文字数のリリース条件セットで指定されている文字数を超えました。 このメッセージを処理できるように、文字数のリリース条件を変更してください。 設定の変更後、バッチ処理システムにメッセージを再送信する必要があります。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、バッチ処理オーケストレーションによって取得された最初のバッチ要素の文字数が、バッチのリリース条件の "インターチェンジ内の最大文字数" プロパティで指定された文字数を超えていたため、バッチ処理オーケストレーションが、バッチ化されたインターチェンジを生成できなかったことを示します。 最大値と比較する文字数には、エンベロープ内の文字数は含まれません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  インターチェンジの受信者となるパーティに対して、[EDI のプロパティ] ダイアログ ボックスの [インターチェンジのバッチ作成用の設定] ページで "インターチェンジ内の最大文字数" プロパティを大きくします。 これを行うには、オーケストレーション インスタンスを停止し、プロパティの最大文字数を大きくしてから、オーケストレーション インスタンスを再起動する必要があります。 送信者にメッセージを再送信してもらいます。  
  
2.  送信者が最大文字数よりも文字数の少ないトランザクション セットを送信するようにします。