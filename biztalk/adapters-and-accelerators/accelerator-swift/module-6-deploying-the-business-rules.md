---
title: 第 6 章:ビジネス ルールの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tutorial, deploying business rules
- deploying, business rules
- business rules
ms.assetid: e8fb8993-3450-4795-80fd-ff28bff8fe97
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 504857e04fc909dc558b0900f23d0d226d82fcf9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377151"
---
# <a name="module-6-deploying-the-business-rules"></a>第 6 章:ビジネス ルールの展開
このモジュールで、インストール ログを確認、および、ビジネス ルール作成ツールを使用してデプロイを確認します。 ビジネス ルールを展開します。  
  
 ビジネス ルールを使用することを確認するマイクロソフト[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]メッセージは、世界銀行間金融電気通信 (SWIFT) 標準の社会で定義されている書式指定、フィールドの仕様、およびネットワークの検証規則に準拠します。 書式指定が全体としてのメッセージの構造に関連し、フィールドの指定が、メッセージ内の各フィールドについて詳しく説明します。 ネットワーク検証規則は、クロス フィールド検証に適用され、本質的に複雑な。  
  
 A4SWIFT では、各メッセージの XSD スキーマの仕様を提供します。 A4SWIFT (逆アセンブラー) を逆アセンブラーとアセンブラー (ASM) は、スキーマを使用して解析またはシリアル化し、ネイティブのフラット ファイル メッセージを検証します。 検証は、書式指定と、スキーマをエンコードするフィールドの指定に制限されます。 ただし、いくつかの形式をエンコードし、スキーマ内で関連する規則をフィールドことはできません。  
  
 A4SWIFT には、以下の SWIFT 標準リリース ガイド (SRG) ビジネス ルールのセットも含まれています。 BizTalk Server ビジネス ルール エンジン (BRE) は、A4SWIFT ポリシーを呼び出すし、A4SWIFT のビジネス ルールを適用します。  
  
 これらのビジネス ルールは、形式とフィールド、およびスキーマの自然な能力を超えているネットワーク検証ルールに関連する複雑な検証のためです。 SWIFT 逆アセンブラーまたは ASM コンポーネントの受信または送信パイプライン内では、BRE を呼び出します。  
  
 変更することでオンまたはオフの検証を有効にする、 **BREValidation**パイプライン内での逆アセンブラーのプロパティ。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [レッスン 1:関連するビジネス ルールを展開する](../../adapters-and-accelerators/accelerator-swift/lesson-1-deploying-the-related-business-rules.md)  
  
-   [レッスン 2:ビジネス ルール作成ツールを使用して展開を確認する](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)