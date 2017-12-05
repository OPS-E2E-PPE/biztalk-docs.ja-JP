---
title: "レッスン 3: SWIFT スキーマをプロジェクトに追加する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12fb5741b75fb9792cbabf46bf7a0402972d7bb4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a>レッスン 3: SWIFT スキーマをプロジェクトに追加します。
ソリューションと、新しいプロジェクトがある場合は、これで、プロジェクトに項目を追加できます。 追加する最初の項目は、MT103 SWIFT 支払いメッセージのスキーマです。 スキーマ テンプレートを選択すると、BizTalk エディターが起動します。  
  
### <a name="to-add-a-new-schema-to-the-project"></a>新しいスキーマをプロジェクトに追加するには、次の操作を行います。  
  
1.  ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントし、**追加**、順にクリック**既存項目の**します。  
  
2.  追加既存項目の SWIFTSchemas ダイアログ ボックスを参照  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Base スキーマ * *。  
  
3.  選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**です。  
  
    > [!NOTE]
    >  SWIFT ベース Types.xsd と SWIFT 共通データ Types.xsd スキーマ SWIFTSchemas プロジェクトの下ソリューション エクスプ ローラーで表示します。  
  
4.  ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントし、**追加**、順にクリック**既存項目の**します。  
  
5.  追加既存項目の SWIFTSchemas ダイアログ ボックスを参照、   **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category 1\MT103** フォルダーです。  
  
6.  選択、 **MT103.xsd**スキーマ、およびクリック**追加**です。  
  
    > [!NOTE]
    >  SWIFTSchemas プロジェクトの下で、ソリューション エクスプ ローラーで、新しいスキーマ MT103.xsd が表示されます。  
  
7.  ソリューション エクスプ ローラーで、 **MT103.xsd** BizTalk エディターでスキーマを表示します。  
  
    > [!NOTE]
    >  (左側のウィンドウ) のスキーマ ツリーと XSD ビュー (右ペイン) には、BizTalk エディターが表示されます。  
  
8.  **ファイル** メニューのをクリックして**すべて保存**して変更を保存します。  
  
 進みます[レッスン 4: ビルドしてアセンブリを配置する](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md)です。