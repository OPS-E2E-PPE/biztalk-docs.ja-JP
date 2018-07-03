---
title: 'レッスン 3: SWIFT スキーマをプロジェクトに追加する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, adding to projects
- projects
ms.assetid: e17ef4b8-f060-44cc-b988-0f9f54deab90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fcaa7f9af0dd802f457f84d7661f92bcdf08157
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982043"
---
# <a name="lesson-3-adding-swift-schemas-to-a-project"></a>レッスン 3: SWIFT スキーマをプロジェクトに追加します。
ソリューションと新しいプロジェクトをプロジェクトに項目を追加できます。 追加する最初の項目は、MT103 SWIFT 支払いメッセージのスキーマです。 スキーマ テンプレートを選択すると、BizTalk エディターが起動します。  
  
### <a name="to-add-a-new-schema-to-the-project"></a>新しいスキーマをプロジェクトに追加するには、次の操作を行います。  
  
1. ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントして、**追加**、 をクリックし、**既存項目の**。  
  
2. 追加する既存の項目-SWIFTSchemas ダイアログ ボックスを参照 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base スキーマ**します。  
  
3. 選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**します。  
  
   > [!NOTE]
   >  SWIFT のベース Types.xsd と SWIFT の一般的なデータ Types.xsd スキーマ SWIFTSchemas プロジェクトの下でソリューション エクスプ ローラーで表示します。  
  
4. ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをポイントして、**追加**、 をクリックし、**既存項目の**。  
  
5. 追加する既存の項目-SWIFTSchemas ダイアログ ボックスを参照、  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\<バージョン\>MessagePack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MT103**フォルダー。  
  
6. 選択、 **MT103.xsd**スキーマ、およびクリック**追加**します。  
  
   > [!NOTE]
   >  ソリューション エクスプ ローラーで、SWIFTSchemas プロジェクト MT103.xsd、新しいスキーマが表示されます。  
  
7. ソリューション エクスプ ローラーでダブルクリック**MT103.xsd** BizTalk エディターでスキーマを表示します。  
  
   > [!NOTE]
   >  スキーマ ツリー (左側のウィンドウ) と XSD ビュー (右側のウィンドウ) には、BizTalk エディターが表示されます。  
  
8. **ファイル** メニューのをクリックして**すべて保存**変更を保存します。  
  
   進みます[レッスン 4: アセンブリの配置のビルドと](../../adapters-and-accelerators/accelerator-swift/lesson-4-building-and-deploying-the-assembly.md)します。