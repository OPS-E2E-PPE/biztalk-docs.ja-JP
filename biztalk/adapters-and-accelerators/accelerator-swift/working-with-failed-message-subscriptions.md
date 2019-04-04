---
title: メッセージのサブスクリプションの失敗の操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, subscriptions
- failed messages, developing
- developing, failed message subscriptions
ms.assetid: 8dee0aa8-53bf-40be-866b-f1b83960dc99
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e4cedf2d47c0bbe8e812795ad428a987d4c2014
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014219"
---
# <a name="working-with-failed-message-subscriptions"></a>失敗したメッセージのサブスクリプションの使用
ときに、Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]逆アセンブラーのプロセス (解析および検証します)、メッセージをそのメッセージのプロパティを昇格します。 これらの昇格させたプロパティは、A4SWIFT 受信バッチの一環として、メッセージを受信した場合、バッチに関連する情報だけでなく、正確性と、メッセージの有効性についての情報を提供します。 これらのプロパティの完全な一覧を参照してください。 [a4swift _ * 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)します。  
  
 ネイティブの BizTalk 逆アセンブラーとは異なり、A4SWIFT 逆アセンブラーはメッセージを保留しない生成エラーや障害を処理するときにします。 代わりに、そのメッセージを発行、失敗したメッセージ ボックス データベースに有効なメッセージと同様です。 その結果、失敗したメッセージはメッセージ ボックス データベースにエラーの詳細を実行できます。 メッセージ ボックス データベースからメッセージを取得、処理し、メッセージを修復しても、メッセージ ボックス データベースにメッセージを再送信できます。 メッセージが実際にあった場合、これらのタスクのほとんどを実行することはできません*中断*します。  
  
 A4SWIFT が昇格させたプロパティによってエラーがあるかどうかと、メッセージ ボックス データベースに公開するメッセージを識別できます。 SWIFT 逆アセンブラーが設定し、昇格失敗したメッセージを処理する際、 **A4SWIFT_Failed**プロパティ、および 1 つ以上のメッセージをメッセージ ボックス データベースに公開する前に、他の次プロパティ。  
  
- **A4SWIFT_ParseErrors**解析処理中に発生 (形式が正しくないデータ) などのエラーの数を示します。  
  
- **A4SWIFT_XmlValidationErrors**処理中に発生した (無効なデータやスキーマに関して型が正しくない) XML 検証のエラーの数を示します。  
  
- **A4SWIFT_BreValidationErrors**処理中に発生した (SWIFT ネットワーク規則に違反するデータ) などのビジネス ルール エンジン (BRE) の検証エラーの数を示します。  
  
- **A4SWIFT_Failed**は**true**任意の数、上記のプロパティが 0 より大きい場合、または**false**カウントが 0 に等しい場合。  
  
  これらのプロパティは、Microsoft のすべての一部です。Solutions.A4SWIFT.Property 名前空間。 これらおよびその他の昇格させたプロパティの詳細については、[a4swift _ * 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)を参照してください。  
  
  Catch または失敗したメッセージを取得、送信ポートのフィルター式 (サブスクリプション) を作成する必要があるまたはオーケストレーションの受信図形を含む、上記のプロパティの一部として**AND**式の句。  
  
  次の句を追加するすべての失敗したメッセージをサブスクライブするなど、(として、 **AND**句の他の句がある場合)。  
  
  Microsoft .Solutions.A4SWIFT.Property.A4SWIFT_Failed == **true**  
  
  解析エラーのみを持つメッセージをサブスクライブするには、加算、次の句。  
  
  **AND** Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **true**、**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_XmlValidationErrors 0、= =**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_BreValidationErrors; 0 = =  
  
  逆に、送信ポートまたはオーケストレーションの有効なメッセージのみを処理するように設計の場合は、"**AND**Microsoft。Solutions.A4SWIFT.Property.A4SWIFT_Failed = = **false**"として、フィルター式の句。  
  
> [!NOTE]
>  サブスクリプションが重なっている場合、A4SWIFT はすべてのサブスクリプションを満たします。 つまり、(送信ポートまたはオーケストレーション) は、複数のサービスには、特定のメッセージによって実行されるフィルター式にある場合、このようなすべてのサービスは、同じメッセージを受け取ります。 たとえば、送信ポートがすべて失敗したメッセージをサブスクライブすると、オーケストレーションは、解析エラー メッセージのみをサブスクライブ、両方のサブスクリプションが満たされる A4SWIFT でメッセージを処理するときに解析エラーが発生したときにします。 サービス間でのサブスクリプションで不要な重複を排除してください。  
> 
> [!NOTE]
>  A4SWIFT 受信メッセージを処理し、MessageBox データベースにそのメッセージを発行するメッセージがすべてのサブスクリプションを満たさない場合は、A4SWIFT はメッセージを中断、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]サブスクライバーがないことを示すエラー。 例では、すべてのメッセージをサブスクライブするサービスがある場合の"A4SWIFT_Failed false = ="、サービスがメッセージをサブスクライブしないが、場所"A4SWIFT_Failed true = ="、サブスクライバーがないのために解析に失敗したメッセージまたは検証を中断するが実際にします。 実際にこのシナリオでは失敗したメッセージの従来の中断を模倣することができます。 中断したくないすべてのメッセージをサブスクライブすることを確認します。 BizTalk Server のヘルプを参照して、メッセージ ボックス データベースのサブスクリプションの詳細については、送信ポート、オーケストレーション、およびフィルター式。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [失敗したメッセージと ErrorCollection オブジェクト](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)