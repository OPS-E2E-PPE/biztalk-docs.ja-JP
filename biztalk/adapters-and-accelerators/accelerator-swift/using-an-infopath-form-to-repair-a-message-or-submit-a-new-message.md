---
title: "メッセージを修復または、新しいメッセージを送信する InfoPath フォームを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- InfoPath forms, verifying messages
- submitting, messages
- InfoPath forms, repairing messages
- Bank Identifier Code (BIC)
- messages, submitting
- messages, repairing
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
- messages, modifying
- messages, InfoPath forms
- modifying, messages
- messages, approving
- repairing messages, InfoPath forms
- messages, creating
- approving messages
- messages, verifying
- verifying, messages
ms.assetid: fb1a885f-fb01-42be-88bc-f68715f689f7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f89959b1900ce03717f2bb28efda7651c5008e7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-infopath-form-to-repair-a-message-or-submit-a-new-message"></a>InfoPath フォームを使用してメッセージを修復または、新しいメッセージを送信
修復、確認、承認、またはメッセージを作成で作業をする、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム内から開くこと、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR Web サイトです。 MRSR サイトに含まれる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]各メッセージの種類のフォームと[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]未解析のメッセージの形式です。 Message Repair and New Submission、開くことができます、適切な MRSR ドキュメント ライブラリに修復、検証、または承認が必要なメッセージを送信します。  
  
 MRSR ドキュメント ライブラリでメッセージを開くときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]が表示されます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム メッセージ データを設定します。 内の操作を実行する、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、ドロップダウン リスト (該当する場合) から値を選択し、フィールドが必須またはオプションがあるかどうかを確認する、ラベルの付いたフィールド内のデータを操作することができます。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Message Repair and New Submission の送信用のドメイン アカウントと証明書で署名を要求することによってプロセスがセキュリティで保護できるようになります。  
  
 内のメッセージに対して操作を実行する、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイトを展開する必要がある、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]そのメッセージの種類のフォームです。 これはロード、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]テンプレート ドキュメント ライブラリに、メッセージに必要な形式です。  
  
## <a name="repairing-a-message"></a>メッセージの修復  
 修復、確認、承認、またはメッセージを作成する MRSR SharePoint サイト内から開かれた InfoPath フォームで作業します。 修復するメッセージは、MRSR サイトで公開されます。 Message Repair and New Submission は、適切な MRSR サイト ドキュメント ライブラリに開くことができます修復、検証、または承認が必要なメッセージを送信します。  
  
 MRSR サイト ドキュメント ライブラリでメッセージを開くと、A4SWIFT メッセージ データが設定される InfoPath フォームが表示されます。 ドロップダウン リスト (該当する場合) から値を選択し、フィールドが必須またはオプションがあるかどうかを確認する、ラベルの付いたフィールド内のデータを操作することにより、InfoPath フォーム内の操作を実行するとします。 A4SWIFT 確実に Message Repair and New Submission の送信用のドメイン アカウントと証明書で署名を要求することによってプロセスがセキュリティで保護されます。  
  
 MRSR サイトでは、メッセージに対して操作を実行するには、そのメッセージの種類の InfoPath フォームを配置する必要があります。 これには、メッセージに必要なテンプレート ドキュメント ライブラリに InfoPath フォームが読み込まれます。  
  
## <a name="verifying-a-message"></a>メッセージの検証  
 修復ワークフローは、検証ステージを含めることができます。 この段階では、修理会社は、メッセージを修復した後、検証機能を確認メッセージの修復が正しいこと。 内のメッセージを開くには、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームから、\<部門名 > _RekeyVerify MRSR サイトでライブラリを文書化し、修復をメッセージに内容が正しいことを確認します。 データを鍵更新、キー更新を必要とする特定のフィールドにもする必要があります。 すべての検証段階は、再生成する必要があります (存在する場合) のフィールドをカスタマイズできますが、キー更新が必要です。 キーの再検証の詳細については、次を参照してください。 [Message Repair and New Submission の特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)です。  
  
 すべての可能なステージで構成されるワークフローには、1 つまたは複数の検証段階が含まれています。 ただし、ワークフローが検証ステージを含める必要はありません。  
  
## <a name="approving-a-message"></a>メッセージを承認します。  
 修復ワークフローは、承認ステージを含めることができます。 この段階では、検証機能ことを確認したら、メッセージ、または、新しいメッセージ内のデータを修復したり、承認者視覚的にことを確認メッセージの修復が正しいこと。 検証ステージで構成されているキーの再検証、承認ステージから成る visual の検証中に注意してください。  
  
## <a name="accepting-or-rejecting-the-changes-to-a-message"></a>承認または拒否するメッセージへの変更  
 ステージを完了すると、作成者、修理会社、検証、または承認者、変更を受け入れる、変更を取り消すか、変更を拒否します。 送信が成功した場合は、承認は、次のステージにメッセージを移動します。 拒否は、拒否された変更と、メッセージを送信します。 キャンセルは、送信プロセスをキャンセルし、メッセージは、現在のステージに残ります。  
  
 確認のメッセージを拒否するステージを承認するか[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ワークフローが定義されている最初のステージにメッセージが返されます (作成または修復) です。 ワークフローをリセットすると、任意の修理会社がメッセージを修復できるようにします。 ワークフローの最初の段階では、メッセージを拒否する場合、修復オーケストレーションは、適切な昇格させたプロパティと一緒にメッセージ ボックス データベースにメッセージを公開します。 これらのメッセージを処理するためのカスタム ハンドラーを記述することができます。 詳細については、次を参照してください。[拒否メッセージのカスタム ハンドラーの作成](../../adapters-and-accelerators/accelerator-swift/creating-a-custom-handler-for-rejected-messages.md)です。  
  
 作成または修復の段階でメッセージを拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを中断し、エラー メッセージが表示されます:「をリセットできませんでした、ワークフローの最初のステージにします」。  
  
## <a name="repairing-an-unparsed-message"></a>未解析のメッセージの修復  
 解析エラーのため、メッセージが失敗した場合は[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR サイトの未解析のドキュメント ライブラリにメッセージをルーティングします。 同様に、メッセージをダブルクリックすると、検証に失敗したメッセージ[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]が表示されます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム メッセージ データを設定します。 フォーム内からメッセージを修復します。 メッセージを送信するときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]送信トレイの検証または承認せずに直接メッセージを送信します。 詳細については、次を参照してください。[未解析のメッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)です。  
  
## <a name="creating-and-submitting-a-new-message"></a>作成して、新しいメッセージを送信します。  
 新しいメッセージを作成することができます、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイトをメッセージに新しいフォームを表示する、データを入力し、管理者に送信します。 詳細については、次を参照してください。[を作成すると、新しいメッセージを送信する](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)です。  
  
 新しいメッセージを作成するには、そのメッセージの種類の新しいメッセージ形式を展開する必要があります。 これには、新しいメッセージのフォームを含むために作成したドキュメント ライブラリに、メッセージに必要な XML 形式が読み込まれます。  
  
 既定の新しいメッセージ形式からメッセージを作成するときに生成されますすべてのフィールドで、すべてのフィールドのデータの入力を求めること。 メッセージを開き、データの入力、保存を実行して、フォームのフィールドに事前設定することができます-MRSR サイトの [ファイル] メニューからのコマンドにします。 付与できる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]別の名前を形成し、別のドキュメント ライブラリに保存します。  
  
## <a name="looking-up-a-bic"></a>BIC の検索  
 作業する際、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイト銀行識別子コード (BIC) を入力する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BIC の検索に使用できるユーティリティを提供します。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、フォームの右側のウィンドウで [BIC 参照] をクリックします。 これには、銀行 name またはその逆に基づく BIC を検索するためのフォームが表示されます。 これによって、検索の Bicplus テーブル、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース。 Bicplus テーブルの詳細については、次を参照してください。[有効にすると検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)と[A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)です。