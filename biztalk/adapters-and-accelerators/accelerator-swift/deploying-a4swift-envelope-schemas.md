---
title: "A4SWIFT エンベロープ スキーマを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8811f1dd056ca5a4ea4582d593af30e2ffc879f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="deploying-a4swift-envelope-schemas"></a>A4SWIFT エンベロープ スキーマを展開します。
Message Repair and New Submission を設定するときに、プロジェクトのスキーマでエンベロープ スキーマを含める必要があります。 エンベロープ スキーマで、EnvelopeMT103.xsd などが MRSR サイトへの書き込みに必要です。  
  
 **概要**  
  
 ようエンベロープ スキーマをプロジェクトに追加します。  
  
-   Visual Studio で、メッセージ スキーマを含むプロジェクトに、各メッセージ スキーマをエンベロープ スキーマを追加します。  
  
-   1 つまたは複数のエンベロープ スキーマを含むすべてのプロジェクトに RuntimeSchemas.dll への参照を追加します。  
  
    > [!NOTE]
    >  RuntimeSchemas.dll への参照を追加することが必要な[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]プロジェクトの Message Repair and New Submission プロジェクトへのエンベロープ スキーマを追加した場合にのみです。  
  
-   未解析のメッセージのエンベロープ スキーマ (EnvelopeUnparsedMessage.xsd) をプロジェクトに追加します。  
  
### <a name="to-add-a-swift-envelope-schema"></a>SWIFT エンベロープ スキーマに追加するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio で、スキーマ プロジェクトを開きます。  
  
2.  右クリック**参照**、クリックして**参照の追加**です。  
  
3.  [参照の追加] ダイアログ ボックス、**参照**タグ。  
  
4.  コンポーネントの選択 ダイアログ ボックスで、開く、**ファイルの場所**ドロップダウン リスト。 移動 ***\<ドライブ\>*: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\Assemblies**です。 選択**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**クリックして、アセンブリの一覧から**追加**です。  
  
5.  **参照の追加**ダイアログ ボックスで、をクリックして**OK**です。  
  
6.  プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の追加**です。  
  
7.  追加で既存の項目 ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Categoryn\MTxxx**です。 たとえば、エンベロープ スキーマを選択**EnvelopeMT103.xsd**、クリックして**追加**です。  
  
     追加で既存の項目 ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動します。 エンベロープ スキーマ、たとえば、EnvelopeMT103.xsd を選択し、[追加] をクリックします。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーで示すように、A4SWIFT は、プロジェクトのエンベロープ スキーマを追加します。  
  
8.  ソリューション エクスプ ローラーでプロジェクトを右クリックし、**追加**、クリックして**既存項目の追加**です。  
  
9. 既存項目の追加 ダイアログ ボックスで、Message Repair and New Submission の機能を使用する場合、**ファイルの場所**ドロップダウン ボックスに移動  **\<*ドライブ*\>: \Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Unparsed メッセージ * *。 選択**EnvelopeUnparsedMessage.xsd**、クリックして**追加**です。  
  
10. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**ビルド**です。  
  
11. ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックして**展開**です。