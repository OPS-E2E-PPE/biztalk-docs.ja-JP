---
title: "バッチ EDI インターチェンジの分割 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29c79b06-cc88-4cc8-aa99-40f24a1bdcde
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441eafe79de57963dc1df5ac19334542f41a23d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="splitting-a-batched-edi-interchange"></a>バッチ EDI インターチェンジの分割
> [!NOTE]
>  このトピックに記載されているすべてのユーザー インターフェイス オプションで使用できる、**ローカル ホスト設定**ページ (**受信者の設定**セクション) の一方向アグリーメント タブの**アグリーメントプロパティ** ダイアログ ボックス。  
  
 EDI 受信パイプラインの分割は受信 EDI インターチェンジのバッチを設定した場合、**受信バッチ処理オプション**アグリーメント プロパティを**トランザクション セットとして分割されたインターチェンジ**です。  
  
 EDI 受信パイプラインが受信バッチ EDI インターチェンジを分割するときには、各トランザクション セット/メッセージにつき 1 つの XML ファイルが作成されます。 EDI 受信パイプラインは、インターチェンジ全体およびグループ ヘッダーを、インターチェンジから分割された各トランザクション セットのコンテキストに昇格させます。 また、ISA6、GS1、GS2 などの特定のインターチェンジおよびグループ ヘッダーを昇格させ、これらのフィールドをルーティングに使用できるようにします。 ヘッダーのセキュリティ情報をマスクするを選択すると、**セキュリティ/認証/パスワード情報をマスク**プロパティです。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でインターチェンジのトランザクション セットへの分割が試行されると、特定の ISA (ISA1 ～ ISA13) または UNB ヘッダー フィールド内のすべてのエラーは、インターチェンジ拒否の原因になります。 これは、アグリーメントまたはフォールバック アグリーメントのプロパティで、重複するインターチェンジ制御番号の有無を確認する機能がオンになっている場合に、インターチェンジ制御番号が重複する場合にも該当します。 他のインターチェンジのヘッダー フィールド (X12 インターチェンジの ISA1 ～ ISA13 以外) およびグループ ヘッダー フィールド内のエラーでは、インターチェンジ処理の失敗は発生しません。  
  
 場合**エラーのトランザクション セットを中断するトランザクション セットとして分割されたインターチェンジ**がアグリーメント プロパティで選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]設定エラーが発生した場合、トランザクションが中断されます。 場合**– のトランザクション セットとして分割されたインターチェンジがエラーでインターチェンジを中断**が選択されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]はインターチェンジを中断します。  
  
 各 XML バッチ要素は MessageBox にルーティングされ、そのバッチ要素をサブスクライブする送信ポートまたはオーケストレーションによって処理されます。 インターチェンジ内のトランザクション セットの順序は、分割メッセージとして処理された後は保持されません。 受信側では、メッセージはインターチェンジに表示された順序に従って処理され、MessageBox に配置されます。ただし、送信側でもそれと同じ順序を維持するには、コンボイまたは順次配送の送信ポートを使用する必要があります。  
  
 バッチから分割された要素が送信バッチに含まれる場合、BatchMarker パイプライン コンポーネントは必須プロパティを昇格させます。 詳細については、次を参照してください。[送信 EDI メッセージのバッチ処理](../core/batching-outgoing-edi-messages.md)です。  
  
## <a name="see-also"></a>参照  
 [受信バッチの処理](../core/processing-incoming-batches.md)   
 [送信 EDI メッセージをバッチ処理](../core/batching-outgoing-edi-messages.md)