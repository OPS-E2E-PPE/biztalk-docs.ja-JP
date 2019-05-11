---
title: バッチ EDI インターチェンジの分割 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a771d499116093b36605d2e3d518774a5b5994c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243231"
---
# <a name="splitting-a-batched-edi-interchange"></a>バッチ EDI インターチェンジの分割
> [!NOTE]
>  このトピックで説明されているすべてのユーザー インターフェイスのオプションが表示されます、**ローカル ホスト設定**ページ (**受信者の設定**セクション) の一方向アグリーメント タブの**アグリーメントプロパティ** ダイアログ ボックス。  
  
 EDI 受信パイプラインの分割、受信 EDI インターチェンジのバッチを設定した場合、**受信バッチ処理オプション**アグリーメント プロパティを**インターチェンジをトランザクション セットとして分割**します。  
  
 EDI 受信パイプラインが受信バッチ EDI インターチェンジを分割、各 EDI トランザクション セット/メッセージの 1 つの XML ファイルが作成されます。 パイプラインはインターチェンジ全体を昇格し、各トランザクションのコンテキストにグループ ヘッダーは、インターチェンジから分割を設定します。 また、ISA6、GS1、GS2 などの特定のインターチェンジおよびグループ ヘッダーを昇格させ、これらのフィールドをルーティングに使用できるようにします。 ヘッダーのセキュリティ情報をマスクするを選択すると、**セキュリティ/認証/パスワード情報をマスク**プロパティ。  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]しようと、インターチェンジのトランザクションに分割すると設定すると、エラーを特定の ISA (ISA1 ~ ISA13) または UNB ヘッダー フィールドは、インターチェンジ拒否につながります。 これは、ケースにもインターチェンジ制御番号が重複するアグリーメントまたはフォールバック アグリーメントのプロパティで、重複するインターチェンジ制御番号のチェックが有効になっている場合。 その他のインターチェンジのヘッダー フィールド内のエラー (X12 の ISA1 ~ ISA13 以外のインターチェンジ) またはグループ ヘッダー フィールドは、インターチェンジの処理が失敗します。  
  
 場合**エラーのトランザクション セットを中断するトランザクション セットとして分割されたインターチェンジ**がアグリーメントのプロパティで選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定エラーが発生した場合、トランザクションが中断されます。 場合 **– のトランザクション セットとして分割されたインターチェンジがエラーでインターチェンジを中断**が選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターチェンジは中断されます。  
  
 各 XML バッチ要素は、MessageBox にルーティングし、送信ポートまたはバッチ要素をサブスクライブするオーケストレーションによって処理します。 分割メッセージとして処理された後、インターチェンジ内のトランザクション セットの順序を保持されません可能性があります。 受信側でメッセージをインターチェンジに表示されるとその順序でメッセージ ボックス内に配置されますが、コンボイを使用する必要がありますまたは順次配送の送信ポート、送信側で順序を維持する順序で処理されます。  
  
 バッチから分割された要素は、送信バッチに含まれているが場合、BatchMarker パイプライン コンポーネントは、必要なプロパティを昇格します。 詳細については、次を参照してください。[送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)します。  
  
## <a name="see-also"></a>参照  
 [受信バッチの処理](../core/processing-incoming-batches.md)   
 [送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)