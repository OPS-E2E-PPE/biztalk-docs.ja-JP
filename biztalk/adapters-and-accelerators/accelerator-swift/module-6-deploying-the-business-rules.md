---
title: "第 6 章: ビジネス ルールの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e890456b7ff3e467a0f513a261d12a52f92689f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="module-6-deploying-the-business-rules"></a>第 6 章: ビジネス ルールの展開
このモジュールで、インストール ログを確認、および、ビジネス ルール作成ツールを使用してデプロイを確認するビジネス ルールを展開します。  
  
 ビジネス ルールを使用していることを確認する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] Worldwide 銀行間財務通信 (SWIFT) 標準の Society で定義されている書式指定、フィールドの仕様、およびネットワーク検証規則に従う必要メッセージ。 書式指定が全体としてメッセージの構造に関連し、フィールドの仕様が、メッセージ内の各フィールドについて詳しく説明します。 ネットワーク検証ルールは、クロス フィールド検証に適用され、本質的に複雑です。  
  
 A4SWIFT は、各メッセージの XSD スキーマの仕様を提供します。 A4SWIFT の逆アセンブラー (DASM) およびアセンブラー (ASM) は、スキーマを使用して解析またはシリアル化し、ネイティブのフラット ファイル メッセージを検証します。 検証は、書式指定とスキーマをエンコードするフィールドの仕様に制限されます。 ただし、いくつかの形式をエンコードし、スキーマ内の関連の規則をフィールドすることはできません。  
  
 A4SWIFT には、以下の SWIFT 標準リリース ガイド (SRG) ビジネス ルールのセットも含まれています。 BizTalk Server ビジネス ルール エンジン (BRE) は、A4SWIFT ポリシーを呼び出すし、A4SWIFT ビジネス規則が適用されます。  
  
 これらのビジネス ルールが形式とフィールド、およびスキーマの自然な能力を超えているネットワーク検証規則に関連する複雑な検証のために含まれます。 SWIFT DASM または ASM コンポーネントの受信または送信パイプライン内では、BRE を呼び出します。  
  
 変更することで、オンまたはオフ、検証を有効にする、 **BREValidation**パイプラインの内部で逆アセンブラーのプロパティです。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [レッスン 1: 関連するビジネス ルールの展開](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [レッスン 2: ビジネス ルール作成ツールを使用して、展開を確認します。](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)