---
title: 未解析メッセージの修復 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
ms.assetid: cc061243-3539-4407-a096-71a3feded1c5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd9e2a19e875df1d666d8a6a72ba92f39b7cc2c4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530036"
---
# <a name="repairing-unparsed-messages"></a>未解析メッセージの修復
場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]逆アセンブラーがメッセージを解析できません、そのメッセージを修復することができます。 行います、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]内からフォーム、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイト。 ただし、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] XML または BRE の検証に失敗した修復されたメッセージから異なる方法では、そのメッセージを処理します。  
  
 メッセージまたはバッチが解析、失敗した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]マークを付けます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed 解析エラー数は 0 より大きい、True を = です。 メッセージ本文は、XML のラッパーに入れ、フラット ファイル形式に残ります。 修復ルールが解析エラーの処理を許可するように設定されている場合、メッセージは、未解析の形式を使用して処理するための未解析の受信トレイに送信されます。  
  
 すべてのユーザーとすべての部門の 1 つだけ未解析の受信トレイがあるため、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]以外の受信場所が、元のメッセージに関するすべてのデータへのアクセスを持てません。 未解析メッセージを修復するには結果としてで、ユーザーが、修復機能があり、修復の役割のすべての部門に関連付けられている必要があります。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 未解析メッセージ、Unparsed のテキスト領域に表示します[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 解析の問題を修正するには、入力または必要に応じて文字を削除することがあります。 送信された後、メッセージが XML ラッパーから抽出され、SWIFT 受信パイプラインを通じて再送信します。 解析が成功すると、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]他のメッセージと同じように、メッセージを処理します。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 完全修復ワークフローを修正する未解析メッセージを処理しません。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 未確認および未承認を送信します。 修復された未解析メッセージの署名を送信すると[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BRE 検証を呼び出すまたは部門のチェックはありませんが、送信パイプラインに直接メッセージを送信します。 パイプラインは、メッセージを処理できない場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復プロセスに送信します。  
  
 このプロセスでは、別のシステムから不適切な形式のメッセージを修正することができます。 ただし、解析の問題を修正するときに警告を使用する必要があります。 ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]未解析メッセージの処理、メッセージは検証されません。 すべてのユーザーがこのプロセスを実行できるように、未解析の修復は、ロールとして定義されていません。 未解析メッセージは、任意の部門に属していない、ため、それらへのアクセスを提供する唯一のセキュリティは、未解析の受信トレイの Acl にします。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] また、元は保持されません受信メッセージのコンテキスト プロパティとして未解析メッセージの場所。  
  
 未解析メッセージに対して実行するカスタム検証を記述することができます。 元のファイルのパイプラインに修復された未解析メッセージを送信するサブスクリプションを記述することもできます。  
  
 未解析メッセージで動作する修復メカニズム、EnvelopeUnparsedMessage.xsd スキーマ メッセージ スキーマを含むアセンブリを追加する必要があります。 詳細については、次を参照してください。 [A4SWIFT スキーマの展開](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)します。