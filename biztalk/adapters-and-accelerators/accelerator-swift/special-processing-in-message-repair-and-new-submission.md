---
title: 特殊な Message Repair and New Submission の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be98399ec9af6d3f513cfe27147d0a5b5c4a81c7
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530002"
---
# <a name="special-processing-in-message-repair-and-new-submission"></a>Message Repair and New Submission で特別な処理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission の機能は、エンタープライズ実装を開発します。 機能には、次の特別な処理がサポートされています。  
  
-   検証キーの更新  
  
-   部門固有のワークフローのサポート (詳細については、次を参照してください[メッセージの修復と新しいメッセージの送信](../../adapters-and-accelerators/accelerator-swift/repairing-messages-and-submitting-new-messages.md)。)。  
  
-   BIC 11 BIC 12 データのエントリ  
  
-   1 つの文字列として BIC フィールドのエントリ  
  
-   解析エラーの修復と再送信の (詳細については、次を参照してください[未解析メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)。)。  
  
-   [保存] コマンドを使用して、進行中の修復を保存しています  
  
-   名前を付けて保存コマンドを使用して新しいテンプレートの作成  
  
## <a name="rekey-verification"></a>検証の再入力します。  
 多くの金融機関のトランザクションの最も重要なフィールドを再入力する 2 つ目のユーザーは作業のチェックの主要な手段です。 2 番目のユーザーに読み取りし、これらのフィールドにデータを認識します。 この操作を確認します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] メッセージの修復またはで作成されたこの機能を提供します[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  
  
 キー更新手順が必要な場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーに表示されるフォームで変更するフィールドを空白。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 引き続き、検証機能は、データを入力するときにその内容を使用できるように作業ウィンドウで、元のメッセージの内容を表示します。 検証ツールでは、この検証なしの変更を許可する場合がありますので、メッセージの他のフィールドは変更しないでください。 代わりに、その他の変更が必要になる場合、検証機能はメッセージ修復を拒否すべきです。  
  
 キー更新手順の後に[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復の結果とキーの更新の結果を比較します。 フィールドの単位で、変更されているフィールドでのみ、この比較を実行します。 2 つのバージョンは、文字ごとに同意しない場合、メッセージをもう一度修復する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] キーの検証が一致していませんでしたし、エラー メッセージのエラー コレクションの一部を追加しますがあることを示します。 検証ツールによって入力されたデータは保存されません。  
  
 変更するフィールドが MRSR フォルダーに MrsrXpathConfig.xml ファイルで指定されて、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]フォルダー。 このファイルには、フィールドを変更して、フィールドの xpath で構成される名前/値ペアが含まれています。 メッセージごとに変更がフィールドを変更するには、このファイルをカスタマイズできます。 変更するフィールドは、通常、メッセージの内容に関連付けられている最も重要な日付、通貨のトランザクションとトランザクションの量を表すものです。  
  
 Message Repair and New Submission のすべての検証手順には、キーの再検証が含まれます。 視認検証は、承認者によって実行されます。  
  
## <a name="entry-of-bic-12-data-as-bic-11"></a>BIC 11 BIC 12 データのエントリ  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] メッセージの論理ターミナル (LT) アドレスの追加の文字の必要性に対応します。 LT アドレスには、データは 11 文字が含まれていますが、SWIFT Alliance アクセス (SAA) には 9 の位置に"X"が LT フィールドが必要です。 正しい中尉選択 SAA にこの余分な文字を示します  
  
 LT アドレスは、FIN ネットワーク経由でメッセージを送信するために使用されます。 SWIFTBound メッセージ (基本的なヘッダー ブロックの LT アドレス フィールド) または入力アプリケーション ヘッダー ブロックの宛先アドレス フィールドの 2 つのフィールドに含めることができますと SWIFT からのメッセージの 2 つのフィールド (基本的なヘッダー ブロックの LT アドレス フィールド、またはLT 内のアドレス、出力アプリケーション ヘッダー ブロック内のメッセージ入力参照)。  
  
 ユーザーは、作成や、メッセージを修復または検証の一部として、フィールドを更新するときに 11 文字を入力する必要があります。 12 文字を含む、LT キーの更新を修復する場合や場合でも、ユーザーは、のみの 11 文字を入力してください。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 12 番目の文字を挿入し、12 文字のフィールドを検証します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BIC とデータベース内のアドレスに対して、11 文字 LT アドレスを検証します。  
  
## <a name="entry-of-bic-fields-as-one-string"></a>1 つの文字列として BIC フィールドのエントリ  
 1 つのフィールドに、BIC を入力できる[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 BIC、それぞれのサブフィールドを持つ 4 つのサブフィールドが含まれています、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 完全な BIC 文字列を 1 つのフィールドに入力した後[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]の 4 つのサブフィールドをそれぞれ設定します。  
  
## <a name="saving-repairs-in-progress"></a>進行中の修復を保存しています  
 修復を中断する必要がある場合は、修復の受信トレイに現在の状態でメッセージを保存できます。 [保存] コマンドを使用してメッセージにチェックするこれを行います。 閉じることができます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]形式し、メッセージをチェック アウト後で、または他のユーザーがチェック アウトできる修復を続行します。 メッセージの履歴を保存先を示します操作、および 2 つ目の修理会社が実行された修復を確認できます。  
  
 ユーザーのローカル コンピューター上の現在の状態で、メッセージを格納する名前を付けて保存コマンドを実行することができます。 これにより、メッセージを付けて保存を実行したユーザーにチェック アウトできます。 ユーザーが閉じることができます、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームし、修復が別のユーザーの完了後に戻ることはできません、メッセージを確認し、修復します。  
  
## <a name="creating-a-new-template"></a>新しいテンプレートの作成  
 新しいメッセージを作成するときは、名前を付けて保存コマンドを実行して、新しいテンプレートを作成できます。 これにより、既存のテンプレートを開き、データ フィールドを追加して、追加のデータを含む既存のテンプレートに基づく新しいテンプレートを作成することができます。 新しい名前を持つテンプレートを保存して、MRSR サイトで新しいメッセージ フォルダーにアクセスできる人物によるテンプレートに基づいて新しいメッセージを作成できます。 テンプレートに基づくメッセージを送信する MRSR サイトにテンプレートを保存する必要があります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 それ以外の場合、エラーが発生するか、フォームを開くことはできません。