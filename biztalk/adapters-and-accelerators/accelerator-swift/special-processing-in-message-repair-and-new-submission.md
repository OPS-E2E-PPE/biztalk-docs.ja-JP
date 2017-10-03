---
title: "特別な処理で、Message Repair and New Submission |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages, rekey verification
- repairing messages, process flow
- rekey verification
- repairing messages
- messages, templates
- messages, rekey verification
- BIC fields
- templates, messages
- BIC-12 data
- messages, process flow
- BIC-11 data
ms.assetid: 0ab729e3-4b67-47d3-84c9-f016318a4c41
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d77d518b080fd84b874c9bb79dedd5173d0a78b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="special-processing-in-message-repair-and-new-submission"></a>Message Repair and New Submission の特別な処理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の機能は、エンタープライズの実装計画を策定します。 機能には、次の特別な処理がサポートされています。  
  
-   検証キー更新  
  
-   部門固有のワークフローのサポート (詳細については、次を参照してください[メッセージの修復と新しいメッセージの送信](../../adapters-and-accelerators/accelerator-swift/repairing-messages-and-submitting-new-messages.md)。)。  
  
-   BIC 11 BIC 12 データ エントリ  
  
-   1 つの文字列として BIC フィールドのエントリ  
  
-   エラーを修復して再送信の解析 (詳細については、次を参照してください[未解析のメッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。)。  
  
-   [保存] コマンドを使用して、進行中の修復を保存  
  
-   名前を付けて保存コマンドを使用して新しいテンプレートの作成  
  
## <a name="rekey-verification"></a>検証を鍵更新します。  
 多くの金融機関の鍵更新トランザクションの最も重要なフィールドに別のユーザーは作業の確認の主な手段です。 この操作は、2 番目のユーザーが、読み取りし、これらのフィールドにデータを理解してあるを確認します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復またはで作成されたメッセージにこの機能を提供[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
 キー更新手順が必要な場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]するにはユーザーに表示形式で再生成するフィールドを空白。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]まだデータを入力するときに、検証はその内容を使用できるように、作業ウィンドウで、元のメッセージの内容を表示します。 検証ツールでは、検証なしの変更を許可するこの可能性がありますので、メッセージの他のフィールドは変更しないでください。 代わりに、検証ツールは、その他の変更が必要になる場合、メッセージの修復を拒否する必要があります。  
  
 キー更新手順の後に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復の結果を含むキー更新の結果を比較します。 されてに再生成、フィールドの単位であるフィールドにのみ、この比較を実行します。 場合は、文字ごとに 2 つのバージョンが一致しません、再度メッセージを修復する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]キーの検証の不一致が存在すること、および、エラー メッセージのエラー収集の部分を追加を示します。 検証の入力データは保存されません。  
  
 フィールドを再生成されるファイルで指定される、MrsrXpathConfig.xml MRSR フォルダーの下に、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]フォルダーです。 このファイルには、フィールドを再生成して、フィールドの xpath から成る名前/値ペアが含まれています。 どのフィールドが各メッセージの再生成するを変更するには、このファイルをカスタマイズすることができます。 再生成するフィールドは、通常、メッセージの内容に関連付けられている最も重要な日付、トランザクション、およびトランザクションの量の通貨を表すものです。  
  
 Message Repair and New Submission のすべての検証手順には、キーの再検証が含まれます。 承認者によって隠れない検証が実行されます。  
  
## <a name="entry-of-bic-12-data-as-bic-11"></a>BIC 11 BIC 12 データ エントリ  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージの論理ターミナル (LT) アドレスの追加の文字の必要性に対応します。 LT アドレスには、データは 11 文字が含まれていますが、SWIFT Alliance アクセス (SAA) には 9 の位置に"X"を LT フィールドが必要です。 この余分な文字することを示します SAA その正しい中尉を選択する必要があります。  
  
 LT アドレスは、FIN ネットワーク経由でメッセージの送信に使用されます。 SWIFTBound メッセージ (基本的なヘッダー ブロックの LT アドレス フィールド) または入力アプリケーション ヘッダー ブロックの宛先アドレス フィールドの 2 つのフィールドに格納できることと SWIFT からのメッセージの 2 つのフィールド (基本ヘッダー ブロックの LT アドレス フィールド、またはLT アドレス アプリケーション ヘッダーの出力ブロックにメッセージ入力リファレンスを参照)。  
  
 ユーザーは、作成や、メッセージを修復または検証の一部として、フィールドを鍵更新時に 11 文字を入力する必要があります。 12 文字が含まれている LT キー更新を修復する場合や場合でも、ユーザーは 11 文字を入力する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]12 番目の文字を挿入し、12 文字のフィールドを検証します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BIC とデータベース内のアドレスに対して、11 文字 LT アドレスを検証します。  
  
## <a name="entry-of-bic-fields-as-one-string"></a>1 つの文字列として BIC フィールドのエントリ  
 1 つのフィールドに、BIC を入力するには[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 BIC がそれぞれに、サブフィールドを持つ 4 つのサブフィールドを含む、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 1 つのフィールドに完全な BIC 文字列を入力した後[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]それぞれ 4 つのサブフィールドを設定します。  
  
## <a name="saving-repairs-in-progress"></a>修復の進行中の保存  
 修復を中断する必要がある場合は、修復の受信トレイに現在の状態でメッセージを保存できます。 [保存] コマンドを使用して、メッセージでチェックするこれを行います。 閉じることができます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]形式し、メッセージをチェック アウト後で、または他のユーザーがチェック アウトの修復を続行します。 メッセージの履歴を示します、保存操作、および 2 番目の修理会社を実行して修復を確認できます。  
  
 ユーザーのローカル コンピューター上の現在の状態でメッセージを格納する名前を付けて保存コマンドを実行することができます。 これにより、名前を付けて実行したユーザーにチェック アウトされてメッセージが残ります。 ユーザーが閉じることができます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームと、修復が別のユーザーの完了後に戻ることはできません、メッセージを確認して修復しています。  
  
## <a name="creating-a-new-template"></a>新しいテンプレートの作成  
 新しいメッセージを作成する場合は、名前を付けて保存コマンドを実行して、新しいテンプレートを作成できます。 これにより、既存のテンプレートを開く、データ フィールドを追加し、追加のデータを含む既存のテンプレートに基づく新しいテンプレートを作成することができます。 新しい名前を持つテンプレートを保存して、テンプレートに基づいて新しいメッセージを作成 MRSR サイトで新しいメッセージ フォルダーにアクセスできるだれもできます。 テンプレートに基づくメッセージを送信する MRSR サイト テンプレートを保存する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 それ以外の場合、エラーが発生するか、フォームを開くことはできません。