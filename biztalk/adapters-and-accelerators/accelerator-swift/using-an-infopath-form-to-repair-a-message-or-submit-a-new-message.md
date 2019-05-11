---
title: メッセージを修復または新しいメッセージを送信する InfoPath フォームを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2f8c9ecb2ef1e4181cabc6b5ac35b2e13058a36
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529639"
---
# <a name="using-an-infopath-form-to-repair-a-message-or-submit-a-new-message"></a>InfoPath フォームを使用してメッセージを修復または新しいメッセージを送信するには
修復、確認、承認、またはメッセージを作成での作業、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]内から開くフォーム、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR Web サイト。 MRSR サイトに含まれる、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]各メッセージの種類のフォームと[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]未解析メッセージの形式。 Message Repair and New Submission は、修復、検証、または承認が必要なメッセージを開くことができます、適切な MRSR ドキュメント ライブラリに送信します。  
  
 MRSR ドキュメント ライブラリでは、メッセージを開くときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]が表示されます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームのメッセージ データが設定されます。 内で操作を実行する、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、(該当する) 場合、リストをドロップダウン リストから値を選択して、フィールドが必須または省略可能かどうかをラベルの付いたフィールド内のデータを操作することができます。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の送信用のドメイン アカウントと証明書で署名を要求することによってセキュリティで保護されたプロセスは、確実です。  
  
 内のメッセージに対して操作を実行する、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR のサイトで展開する必要がある、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]そのメッセージの種類のフォームです。 これをロード、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]テンプレート ドキュメント ライブラリにメッセージに必要なフォーム。  
  
## <a name="repairing-a-message"></a>メッセージの修復  
 修復、確認、承認、またはメッセージを作成する MRSR SharePoint サイト内から開くことが InfoPath フォームで作業します。 修復するメッセージは、MRSR サイトで公開されます。 Message Repair and New Submission は、修復、検証、または承認が必要なメッセージを開くことができます、適切なの MRSR サイト ドキュメント ライブラリに送信します。  
  
 MRSR サイト ドキュメント ライブラリにメッセージを開くと、A4SWIFT メッセージ データを含む InfoPath フォームが表示されます。 (該当する) 場合、リストをドロップダウン リストから値を選択して、フィールドが必須または省略可能かどうかをラベルの付いたフィールド内のデータを操作することができる InfoPath フォーム内で操作を実行するとします。 A4SWIFT はで Message Repair and New Submission の送信用のドメイン アカウントと証明書で署名を要求することによってプロセスがセキュリティで保護されたことです。  
  
 MRSR サイトでのメッセージに対して、操作を実行するには、そのメッセージの種類の InfoPath フォームを配置する必要があります。 これには、メッセージに必要なテンプレート ドキュメント ライブラリに InfoPath フォームが読み込まれます。  
  
## <a name="verifying-a-message"></a>メッセージの検証  
 修復のワークフローでは、検証ステージを含めることができます。 この段階で、修理会社が、メッセージを修復した後検証機能を検証メッセージの修復が正しいこと。 内のメッセージを開くには、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームから、\<部門名\>_RekeyVerify ドキュメント、MRSR サイト内のライブラリと、メッセージの修復が正しいことを確認します。 キーの更新を必要とする特定のフィールドにデータを再入力する必要があります。 フィールド (ある場合) を変更する必要がありますをカスタマイズできますが、キーの更新のすべての検証段階に必要です。 キーの再検証の詳細については、次を参照してください。 [Message Repair and New Submission で特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)します。  
  
 可能なすべての段階から成るワークフローには、1 つまたは複数の検証段階が含まれます。 ただし、ワークフローが検証ステージを含める必要はありません。  
  
## <a name="approving-a-message"></a>メッセージの承認  
 修復のワークフローでは、承認ステージを含めることができます。 この段階で検証した後、検証はメッセージ、または新しいメッセージのデータを修復承認者視覚的に確認メッセージの修復が正しいこと。 検証ステージで構成されているキーの再検証、承認ステージから成る visual 検証中に注意してください。  
  
## <a name="accepting-or-rejecting-the-changes-to-a-message"></a>許可または拒否メッセージへの変更  
 段階を完了すると、作成者、修理会社、検証、または承認者、変更を受け入れる、変更をキャンセルするか、変更を拒否します。 送信が成功した場合は、承認は、次のステージにメッセージを移動します。 拒否は、拒否の変更によって、メッセージを送信します。 キャンセルは、送信プロセスをキャンセルし、メッセージは、現在のステージに残ります。  
  
 確認のメッセージを拒否するか、または承認ステージでは場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]そのワークフローに対して定義されている最初のステージにメッセージが返されます (作成するか修復) します。 ワークフローをリセットすると、任意の修理会社がメッセージを修復できるようにします。 ワークフローの最初の段階では、メッセージを拒否する場合、修復オーケストレーションはメッセージを適切な昇格させたプロパティと一緒にメッセージ ボックス データベースに発行します。 これらのメッセージを処理するためのカスタム ハンドラーを記述することができます。 詳細については、次を参照してください。[拒否メッセージのカスタム ハンドラーを作成する](../../adapters-and-accelerators/accelerator-swift/creating-a-custom-handler-for-rejected-messages.md)します。  
  
 作成または修復段階でメッセージを拒否した場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージを保留し、エラー メッセージが表示されます。「をリセットできませんでした、ワークフローの最初のステージを。」  
  
## <a name="repairing-an-unparsed-message"></a>未解析メッセージの修復  
 解析のエラーによりメッセージが失敗した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MRSR サイト内の未解析のドキュメント ライブラリにメッセージをルーティングします。 メッセージをダブルクリックすると、検証に失敗したメッセージと同様[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]が表示されます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームのメッセージ データが設定されます。 フォーム内からメッセージを修復します。 メッセージを送信するときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]認証または承認なし送信トレイに直接メッセージを送信します。 詳細については、次を参照してください。[未解析メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)します。  
  
## <a name="creating-and-submitting-a-new-message"></a>作成して、新しいメッセージを送信します。  
 新しいメッセージを作成することができます、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイトを新しいメッセージ フォームの表示、データを入力し、送信します。 詳細については、次を参照してください。[を作成すると、新しいメッセージを送信する](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)します。  
  
 新しいメッセージを作成するには、そのメッセージの種類の新しいメッセージ形式を展開する必要があります。 これには、新しいメッセージのフォームを含むに作成したドキュメント ライブラリにメッセージに必要な XML フォームが読み込まれます。  
  
 既定の新しいメッセージの形式からメッセージを作成するときに設定されますフィールドの中で、すべてのフィールドにデータを入力する必要はありません。 フォームのフィールドをメッセージを開いて、データの入力、保存を実行し、事前に設定することができます-MRSR サイトの [ファイル] メニューからコマンドとして。 与えることができます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]別の名前を形成し、別のドキュメント ライブラリに保存します。  
  
## <a name="looking-up-a-bic"></a>BIC を参照  
 作業する際、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイトでは、銀行の識別子コード (BIC) を入力する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BIC、検索に使用できるユーティリティを提供します。 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームで、フォームの右側のウィンドウで BIC 参照をクリックします。 これには、銀行の名前、またはその逆に基づく BIC を検索するためのフォームが表示されます。 これによって、検索の Bicplus テーブル、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース。 Bicplus テーブルの詳細については、次を参照してください。[を有効にする検証の銀行識別コード](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)と[A4SWIFT データベース内の Bicplus テーブルを管理する](../../adapters-and-accelerators/accelerator-swift/managing-the-bicplus-table-in-the-a4swift-database.md)します。