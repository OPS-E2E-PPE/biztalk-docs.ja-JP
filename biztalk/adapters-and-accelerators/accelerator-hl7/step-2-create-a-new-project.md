---
title: "手順 2: 新しいプロジェクトの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, projects
- projects, creating
- message enrichment tutorial, projects
ms.assetid: 6e994845-53b8-4de8-a64f-32d36f7b5412
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78cfd1341100fe803679e81300609962a9c0e1f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-a-new-project"></a>手順 2: 新しいプロジェクトを作成します。
使用して新しいソリューションをビルドするこの手順で、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]環境。 最初に、(データ型、セグメント、およびテーブルの値) の一般的なスキーマの 3 つ HL7 V2.2 スキーマを使用して、送信 HL7 メッセージに使用するスキーマなどを含む新しいプロジェクト (BTAHL7V22Common) を作成します。 次に、別新しいプロジェクトをビルドする (BTAHL7V2XCommon) HL7 メッセージ (MSH_25_GLO_DEF) 内のヘッダーに使用される共通の標準的なスキーマが含まれています。  
  
### <a name="to-create-a-new-project"></a>新しいプロジェクトを作成するには  
  
1.  開始 **[!INCLUDE[vs2012](../../includes/vs2012-md.md)]**です。  
  
2.  **[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。  
  
3.  新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダーをクリックして、 **BTAHL7Projects**フォルダーです。  
  
4.  **テンプレート** ウィンドウで、をクリックして**BTAHL7V22Common プロジェクト**です。  
  
5.  **名前**フィールドに「 **BTAHL7V22Common**プロジェクト名として。  
  
6.  **場所**フィールドに「 *\<ドライブ >***: \Tutorial**クリックして、パスとして**OK** 、新しいプロジェクトを開きます。  
  
    > [!NOTE]
    >  BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、3 つの一般的なスキーマを新しいプロジェクトをソリューション エクスプ ローラーに追加します。  
  
    -   datatypes_22.xsd  
  
    -   segments_22.xsd  
  
    -   tablevalues_22.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ファイル、プロジェクト フォルダーを作成して、 \<*ドライブ*>: \Tutorial\BTAHL7V22Common フォルダーです。  
  
7.  **[ファイル]** メニューの **[新規作成]**をポイントし、 **[プロジェクト]**をクリックします。  
  
8.  新しいプロジェクト ダイアログ ボックスで、展開、 **BizTalk プロジェクト**フォルダーをクリックして、 **BTAHL7Projects**フォルダーです。  
  
9. **テンプレート** ウィンドウで、をクリックして**BTAHL7V2XCommon プロジェクト**です。  
  
10. **名前**フィールドに「 **BTAHL7V2XCommon**プロジェクト名として。  
  
11. **場所**フィールドに「 *\<ドライブ >***: \Tutorial**パスとして。  
  
12. **ソリューション**フィールドを選択**ソリューションに追加**、順にクリック**OK**です。  
  
    > [!NOTE]
    >  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]次のスキーマで、ソリューション エクスプ ローラーに新しいプロジェクトを追加します。  
  
    -   ACK_24_GLO_DEF.xsd  
  
    -   ACK_25_GLO_DEF.xsd  
  
    -   MSH_25_GLO_DEF.xsd  
  
     [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ファイル、プロジェクト フォルダーを作成して、 **\<ドライブ >: \Tutorial\BTAHL7V22Common\BTAHL72XCommon**フォルダーです。  
  
 進みます[手順 3: アセンブリに厳密な名前を割り当てます](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)です。  
  
## <a name="see-also"></a>参照  
 [メッセージの強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)