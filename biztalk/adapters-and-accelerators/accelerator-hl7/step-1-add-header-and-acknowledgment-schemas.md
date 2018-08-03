---
title: '手順 1: ヘッダーと確認スキーマの追加 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae0712e2ee4498b8f6f2eb8cb9527aa8ee8e4582
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011317"
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a>手順 1: ヘッダーと確認スキーマを追加します。
この手順では、BTAHL72XCommon プロジェクト テンプレートに基づいて新しいプロジェクトを作成します。 このテンプレートには、メッセージ ヘッダー (MSH_25_GLO_DEF.xsd) および受信確認 (ACK_24_GLO_DEF.xsd) の 3 つの一般的なスキーマが含まれています (ACK_25_GLO_DEF.xsd) とします。 そのためのプロジェクトでこれらのスキーマを含める必要がありますを BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ビルドまたはメッセージ ヘッダーと受信確認を正しく検証します。 このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X。  
  
 アセンブリに割り当てること、およびアセンブリを展開しても強力なキーを作成します。 強力なキーでは、アセンブリのセキュリティと id を提供します、展開に必要です。 アセンブリを展開するときに、構成データベース (BizTalk 管理データベースとも呼ばれます) と、グローバル アセンブリ キャッシュ (GAC) に格納されます。  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a>プロジェクトを作成し、ヘッダーと受信確認のスキーマを追加するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
2. 新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、 をクリックし、 **BTAHL7Projects**します。  
  
3. **テンプレート**一覧で、 **BTAHL7V2XCommon プロジェクト**します。  
  
4. **名前**ボックスに「 **BTAHL7V2XCommon**プロジェクト名として。  
  
5. **場所**ボックスを参照する**\<**<em>ドライブ</em>**:\>\Batching チュートリアル**します。  
  
6. **[OK]** をクリックします。  
  
> [!NOTE]
>  ソリューション エクスプ ローラーでプロジェクトの 3 つのスキーマ (MSH_25_GLO_DEF.xsd、ACK_24_GLO_DEF.xsd、および ACK_25_GLO_DEF.xsd) が含まれます。  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a>アセンブリに厳密なキーを割り当てるし、デプロイするには  
  
1. 開いている**Visual Studio コマンド プロンプト**します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、 **\<**<em>ドライブ</em>**\>: \Batching チュートリアル**フォルダー。  
  
3. コマンド プロンプトで「 **sn – k key.snk**し、ENTER キーを押します。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
   > [!NOTE]
   >  適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリのトラブルシューティングを行う。  
  
4. ソリューション エクスプ ローラーで右クリックして**BTAHL7V2Xcommon プロジェクト**、 をクリックし、**プロパティ**します。  
  
5. **BTAHL7V2XCommon プロジェクトのプロパティ ページ**ダイアログ ボックスで、をクリックして**署名**します。  
  
6. 確認**アセンブリに署名**チェック ボックスをオンします。  
  
7. **厳密な名前を選択**キー ファイルのドロップダウン リストを**\<を参照しています\>**.  
  
8. 参照\<*ドライブ*\>: \Batching チュートリアルでは、選択**key.snk**、 をクリックし、**オープン**します。  
  
9. BTAHL7V2XCommon プロジェクト プロパティ ページ ウィンドウで、次のようにクリックします。 **OK** 、変更を保存します。  
  
10. ソリューション エクスプ ローラーで右クリックして**BTAHL7V2Xcommon プロジェクト**、 をクリックし、**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  デプロイの適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デプロイのトラブルシューティングを行う。  
  
    続行する[手順 2: v2.3.1 の一般的なスキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)します。