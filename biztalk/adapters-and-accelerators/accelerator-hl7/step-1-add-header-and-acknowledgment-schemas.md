---
title: "手順 1: 追加のヘッダーと受信確認スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808132bf-02e7-4ff4-b914-9fae5d27e5fd
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f79778801b1ca70d4e8356a24886c792fe447e33
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-1-add-header-and-acknowledgment-schemas"></a>手順 1: ヘッダーと受信確認スキーマを追加します。
この手順では、BTAHL72XCommon プロジェクト テンプレートに基づく新しいプロジェクトを作成します。 このテンプレートには、メッセージ ヘッダー (MSH_25_GLO_DEF.xsd) と受信確認 (ACK_24_GLO_DEF.xsd) の 3 つの一般的なスキーマが含まれています (ACK_25_GLO_DEF.xsd) とします。 そのためのプロジェクトでこれらのスキーマを含める必要がありますを BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ビルドや、メッセージ ヘッダーと受信確認を正しく検証します。 このプロセスは、すべてのスキーマ バージョンの間で共通[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.X です。  
  
 アセンブリに割り当てること、およびアセンブリを展開しても強力なキーを作成します。 強力なキーは、アセンブリのセキュリティと id を提供し、展開に必要なです。 アセンブリを展開するときに、構成データベース (BizTalk 管理データベースとも呼ばれます) と、グローバル アセンブリ キャッシュ (GAC) に格納されます。  
  
### <a name="to-create-the-project-and-add-header-and-acknowledgment-schemas"></a>プロジェクトを作成し、ヘッダーと受信確認のスキーマを追加するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の**ファイル** メニューのをポイント**新規**、クリックして**プロジェクト**です。  
  
2.  新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、順にクリック**BTAHL7Projects**です。  
  
3.  **テンプレート**一覧で、クリックして**BTAHL7V2XCommon プロジェクト**です。  
  
4.  **名前**ボックスに、入力**BTAHL7V2XCommon**プロジェクト名として。  
  
5.  **場所**ボックスを参照 **\<** *ドライブ***:\>\Batching チュートリアル**です。  
  
6.  **[OK]**をクリックします。  
  
> [!NOTE]
>  ソリューション エクスプ ローラーで、3 つのスキーマ (MSH_25_GLO_DEF.xsd、ACK_24_GLO_DEF.xsd、および ACK_25_GLO_DEF.xsd) は、プロジェクトに含まれます。  
  
### <a name="to-assign-a-strong-key-to-the-assembly-and-deploy"></a>アセンブリに厳密なキーを割り当てるし、展開するには  
  
1.  開いている**Visual Studio コマンド プロンプト**です。  
  
2.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、参照、  **\<** *ドライブ***\>: \Batching チュートリアル**フォルダーです。  
  
3.  コマンド プロンプトで次のように入力します。 **sn – k key.snk**、ENTER キーを押します。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
    > [!NOTE]
    >  使用して、適切なメッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリをトラブルシューティングします。  
  
4.  ソリューション エクスプ ローラーで右クリック**BTAHL7V2Xcommon プロジェクト**、クリックして**プロパティ**です。  
  
5.  **BTAHL7V2XCommon プロジェクトのプロパティ ページ**ダイアログ ボックスで、をクリックして**署名**です。  
  
6.  確認**アセンブリに署名**チェック ボックスをオンします。  
  
7.  **厳密な名前を選択して**キー ファイルのドロップダウン リストを**\<を参照しています...\>**.  
  
8.  参照\<*ドライブ*\>: \Batching チュートリアルでは、選択**key.snk**、クリックして**開く**です。  
  
9. BTAHL7V2XCommon プロジェクト プロパティ ページ ウィンドウで、をクリックして**OK**して変更を保存します。  
  
10. ソリューション エクスプ ローラーで右クリック**BTAHL7V2Xcommon プロジェクト**、クリックして**展開**です。 成功メッセージが出力ウィンドウに表示を確認します。  
  
    > [!NOTE]
    >  使用して、正しい配置メッセージが表示されない場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]展開のトラブルシューティングにします。  
  
 進みます[手順 2: v2.3.1 の一般的なスキーマを追加](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)です。