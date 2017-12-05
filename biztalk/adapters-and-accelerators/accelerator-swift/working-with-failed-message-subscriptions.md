---
title: "メッセージのサブスクリプションの失敗の操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6540259fd6983fd418e57ff700de3f1b550016ec
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="working-with-failed-message-subscriptions"></a>失敗したメッセージのサブスクリプションの操作
ときに、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラー プロセス (解析し、検証) メッセージ、そのメッセージのプロパティを昇格させます。 これらの昇格させたプロパティは、A4SWIFT 受信バッチの一部としてメッセージを受信した場合、正しいことと、メッセージの有効性に関する情報と、バッチに関連する情報を提供します。 これらのプロパティの完全な一覧を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。  
  
 ネイティブの BizTalk 逆アセンブラーとは異なり、A4SWIFT 逆アセンブラーはメッセージを保留できません生成エラーや失敗を処理するときにします。 代わりに、発行、失敗したメッセージをメッセージ ボックス データベースに有効なメッセージの場合と同様です。 その結果、失敗したメッセージはメッセージ ボックス データベースにエラーの詳細を実行できます。 メッセージ ボックス データベースからメッセージを取得、処理し、メッセージの修復し、も、メッセージ ボックス データベースにメッセージを再送信します。 メッセージが実際に場合は、これらのタスクのほとんどを実行することはできません*中断*です。  
  
 A4SWIFT が昇格させたプロパティによって失敗またはエラーとして、メッセージ ボックス データベースに公開するメッセージを識別できます。 SWIFT の逆アセンブラーに入力し、昇格、失敗したメッセージを処理する際、 **A4SWIFT_Failed**プロパティ、および 1 つ以上の他の次のプロパティ、メッセージ ボックス データベースにメッセージを発行する前に。  
  
-   **A4SWIFT_ParseErrors**解析処理中に発生した (形式が正しくないデータなど) のエラーの数を示します。  
  
-   **A4SWIFT_XmlValidationErrors**処理中に発生した (無効なデータ スキーマに関して型が正しくないなど) XML 検証のエラーの数を示します。  
  
-   **A4SWIFT_BreValidationErrors**処理中に発生した (SWIFT ネットワーク規則に違反するデータの場合) などのビジネス ルール エンジン (BRE) の検証エラーの数を示します。  
  
-   **A4SWIFT_Failed**は**true**任意の数、上記のプロパティが 0 より大きい場合または**false**カウントが 0 に等しい場合。  
  
 これらのプロパティのすべての一部である、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.A4SWIFT.Property 名前空間です。 これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。  
  
 キャッチまたは失敗したメッセージを取得、送信ポートのフィルター式 (サブスクリプション) を作成する必要がありますまたはオーケストレーションの受信図形を含む、上記のプロパティの一部として**AND**式の句。  
  
 次の句を追加するすべての失敗したメッセージをサブスクライブ、たとえば、(として、 **AND**句の他の句がある場合)。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.A4SWIFT.Property.A4SWIFT_Failed = =**は true。**  
  
 解析エラーのみを持つメッセージをサブスクライブするには、加算、次の句。  
  
 **および**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **true**、**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors = = 0、**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors = = 0 になります。  
  
 逆に、送信ポートまたはオーケストレーションの有効なメッセージのみを処理するように設計の場合は、"**AND**[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]です。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **false**"として、フィルター式の句。  
  
> [!NOTE]
>  サブスクリプションが重なると、A4SWIFT はすべてのサブスクリプションを満たします。 つまり、(送信ポートまたはオーケストレーション) の複数のサービスが、特定のメッセージによって実行されるフィルター式を持つ、このようなすべてのサービスすると、同じメッセージが表示されます。 たとえば、すべての失敗したメッセージをサブスクライブする送信ポート、オーケストレーションは、解析エラー メッセージのみをサブスクライブする場合は、両方のサブスクリプションが満たさ A4SWIFT でメッセージを処理するときに解析エラーが発生したときにします。 サービス間でのサブスクリプションに不要な重複を排除することを確認します。  
  
> [!NOTE]
>  A4SWIFT のメッセージは中断されます A4SWIFT を受信および処理し、メッセージをメッセージ ボックス データベースにそのメッセージを公開、メッセージは任意のサブスクリプションを満たさない場合は、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サブスクライバーが不足していることを示すエラーです。 たとえば、すべてのメッセージをサブスクライブするサービスがある場合"A4SWIFT_Failed = = false"、サービスがメッセージをサブスクライブありませんが、ここで"A4SWIFT_Failed = = true"、解析に失敗したメッセージまたは検証が実際に中断サブスクライバーがないのため、します。 実際には、このシナリオでは、失敗したメッセージの従来の中断を模倣できます。 中断したくないすべてのメッセージをサブスクライブすることを確認します。 BizTalk Server のヘルプを参照して、メッセージ ボックス データベースのサブスクリプションの詳細については、送信ポート、オーケストレーション、およびフィルター式です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [失敗したメッセージと ErrorCollection オブジェクト](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)