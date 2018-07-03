---
title: '手順 2: 新しいプロジェクトの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e17dccc7ef83114fe17c26b03aaa8d06f7ac783
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994651"
---
# <a name="step-2-create-a-new-project"></a>手順 2: 新しいプロジェクトを作成します。
この手順で、Microsoft を使用して新しいソリューションをビルドする[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]環境。 最初に、(データ型、セグメント、およびテーブルの値) の一般的なスキーマの 3 つ HL7 V2.2 スキーマを使用して、使用する送信の HL7 メッセージ スキーマなどを含む新しいプロジェクト (BTAHL7V22Common) を作成します。 次に、もう 1 つ新しいプロジェクトをビルドする (BTAHL7V2XCommon) HL7 メッセージ (MSH_25_GLO_DEF) のヘッダーに使用される共通の標準的なスキーマが含まれています。  
  
### <a name="to-create-a-new-project"></a>新しいプロジェクトを作成するには  
  
1. 開始**Visual Studio**します。  
  
2. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
3. 新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダー、およびクリック、 **BTAHL7Projects**フォルダー。  
  
4. **テンプレート**ウィンドウで、をクリックして**BTAHL7V22Common プロジェクト**します。  
  
5. **名前**フィールドに「 **BTAHL7V22Common**プロジェクト名として。  
  
6. **場所**フィールドに「 *\<ドライブ\>* * *:\Tutorial** パス、およびクリックとして **[ok]** 、新しいプロジェクトを開きます。  
  
   > [!NOTE]
   >  BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 3 つの一般的なスキーマを使用したソリューション エクスプ ローラーに新しいプロジェクトを追加します。  
  
   - datatypes_22.xsd  
  
   - segments_22.xsd  
  
   - tablevalues_22.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] プロジェクト フォルダーを作成し、ファイル、 \<*ドライブ*\>: \Tutorial\BTAHL7V22Common フォルダー。  
  
7. **[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。  
  
8. 新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダー、およびクリック、 **BTAHL7Projects**フォルダー。  
  
9. **テンプレート**ウィンドウで、をクリックして**BTAHL7V2XCommon プロジェクト**します。  
  
10. **名前**フィールドに「 **BTAHL7V2XCommon**プロジェクト名として。  
  
11. **場所**フィールドに「 *\<ドライブ\>* * *:\Tutorial** パスとして。  
  
12. **ソリューション**フィールドで、**ソリューションに追加**、順にクリックします**OK**します。  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 次のスキーマを使用したソリューション エクスプ ローラーに新しいプロジェクトを追加します。  
  
    - ACK_24_GLO_DEF.xsd  
  
    - ACK_25_GLO_DEF.xsd  
  
    - MSH_25_GLO_DEF.xsd  
  
      [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] プロジェクト フォルダーを作成し、ファイル、 **\<ドライブ\>: \Tutorial\BTAHL7V22Common\BTAHL72XCommon**フォルダー。  
  
    進みます[手順 3: アセンブリに厳密な名前を割り当てる](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)します。  
  
## <a name="see-also"></a>参照  
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)