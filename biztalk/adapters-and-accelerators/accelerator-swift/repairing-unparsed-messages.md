---
title: "未解析のメッセージの修復 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
ms.assetid: cc061243-3539-4407-a096-71a3feded1c5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de427afc854bf782f69a8c0428a874c61ffb5c4f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="repairing-unparsed-messages"></a>未解析のメッセージの修復
場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]逆アセンブラーがメッセージを解析できません、そのメッセージを修復することができます。 そのために操作を行う、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]内からのフォーム、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MRSR サイトです。 ただし、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] XML または BRE の検証に失敗した修復されたメッセージを異なるそのメッセージを処理します。  
  
 メッセージまたはバッチは、解析が失敗した場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]としてマークを付けます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed 0 より大きい値の解析エラーの数と True を = です。 メッセージの本文は XML ラッパーに入れ、フラット ファイル形式になります。 修復ルールが解析エラーの処理を許可するように設定されている場合、メッセージは未解析のフォームを使用して処理するため、未解析の受信トレイに送信します。  
  
 すべてのユーザーとすべての部門では、1 つだけ未解析の受信トレイがあるため[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]元の場所が表示される場合を除いて、メッセージに関するデータへのアクセスをいない可能性があります。 その結果、未解析のメッセージを修復するにユーザーの修復機能が必要であり、すべての部門で修復役割に関連付けられたことがあります。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]未解析のメッセージ、テキストの領域に表示、Unparsed[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム。 解析の問題を解決するには、入力または必要な文字を削除することがあります。 送信された後、メッセージが XML ラッパーから抽出され、SWIFT 受信パイプラインを通じて再送信します。 解析が成功すると、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]他のメッセージと同様に、メッセージを処理します。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]完全修復ワークフローを修正した未解析のメッセージを処理しません。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]未確認および未承認を送信します。 修復未解析のメッセージに署名して、送信すると[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BRE 検証を呼び出すまたは部門のチェックはありませんが、送信パイプラインに直接メッセージを送信します。 そのパイプラインは、メッセージを処理できない場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復プロセスに送信します。  
  
 このプロセスでは、別のシステムから不適切な形式のメッセージを解決することができます。 ただし、解析を行って問題を修正するときに注意を使用する必要があります。 ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]未解析のメッセージを処理するメッセージを検証しません。 未解析の修復は、すべてのユーザーがこのプロセスを実行できるように、ロールとして定義されていません。 未解析のメッセージは、その他の部門に属していない、ために、それらへのアクセスを提供しているだけのセキュリティは、未解析の受信トレイの Acl です。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]元が保持されない、メッセージのコンテキスト プロパティと、未解析のメッセージの場所を受信します。  
  
 修復未解析のメッセージに対して実行するカスタム検証を記述することができます。 元のファイル パイプラインに修復された解析されていないメッセージを送信するサブスクリプションを作成することもできます。  
  
 未解析のメッセージで動作する修復メカニズム、EnvelopeUnparsedMessage.xsd スキーマ メッセージ スキーマを含むアセンブリを追加する必要があります。 詳細については、次を参照してください。 [A4SWIFT のスキーマを展開する](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)です。