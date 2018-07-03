---
title: A4SWIFT エンベロープ スキーマの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, envelope schemas
- A4SWIFT, deploying envelope schemas
- envelope schemas
- schemas, envelope schemas
ms.assetid: 6440608c-d30d-4d82-827a-8a4b2738db85
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae07b6b957f608e89c3ae65802d6627440201a65
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004147"
---
# <a name="deploying-a4swift-envelope-schemas"></a>A4SWIFT エンベロープ スキーマの展開
Message Repair and New Submission を設定するたびに、プロジェクトのスキーマでエンベロープ スキーマを含める必要があります。 エンベロープ スキーマで、EnvelopeMT103.xsd などが MRSR サイトへの書き込みに必要です。  
  
 **概要**  
  
 ようエンベロープ スキーマをプロジェクトに追加します。  
  
- Visual Studio で、メッセージ スキーマを含むプロジェクトに、各メッセージ スキーマをエンベロープ スキーマを追加します。  
  
- 1 つまたは複数のエンベロープ スキーマを含む任意のプロジェクトに RuntimeSchemas.dll への参照を追加します。  
  
  > [!NOTE]
  >  RuntimeSchemas.dll への参照を追加することが必要な[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Message Repair and New Submission をプロジェクトにエンベロープ スキーマを追加した場合にのみのプロジェクトします。  
  
- 未解析メッセージのエンベロープ スキーマ (EnvelopeUnparsedMessage.xsd) をプロジェクトに追加します。  
  
### <a name="to-add-a-swift-envelope-schema"></a>SWIFT エンベロープ スキーマに追加するには  
  
1.  ソリューション エクスプ ローラーの Visual Studio でスキーマ プロジェクトを開きます。  
  
2.  右クリック**参照**、 をクリックし、**参照の追加**します。  
  
3.  [参照の追加] ダイアログ ボックスで、**参照**タグ。  
  
4.  コンポーネントの選択 ダイアログ ボックスで、開く、**検索**ドロップダウン リスト。 移動 ***\<ドライブ\>*:\Program \microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\Assemblies**します。 選択**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll**クリックして、アセンブリの一覧から**追加**します。  
  
5.  **参照の追加**ダイアログ ボックスで、をクリックして**OK**します。  
  
6.  プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の追加**します。  
  
7.  追加で既存の項目 ダイアログ ボックスで、**検索**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\ Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Categoryn\MTxxx**します。 たとえば、エンベロープ スキーマを選択**EnvelopeMT103.xsd**、 をクリックし、**追加**します。  
  
     追加で既存の項目 ダイアログ ボックスで、**検索**ドロップダウン ボックスに移動します。 エンベロープ スキーマ、たとえば、EnvelopeMT103.xsd を選択し、[追加] をクリックします。  
  
    > [!NOTE]
    >  A4SWIFT は、ソリューション エクスプ ローラーで示すように、プロジェクトのエンベロープ スキーマを追加します。  
  
8.  ソリューション エクスプ ローラーでプロジェクトを右クリックして**追加**、 をクリックし、**既存項目の追加**します。  
  
9. [既存項目の追加] ダイアログ ボックスで、Message Repair and New Submission 機能を使用する場合、**検索**ドロップダウン ボックスに移動 **\<*ドライブ*\>: \Microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Unparsed メッセージ**します。 選択**EnvelopeUnparsedMessage.xsd**、 をクリックし、**追加**します。  
  
10. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。  
  
11. ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。