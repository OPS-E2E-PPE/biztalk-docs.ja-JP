---
title: '手順 1: を作成し、一般的なヘッダーと確認スキーマの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, headers
ms.assetid: e0f11f58-9a8c-4567-a537-3d182fa7dce2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 988c2922d09412aa248c08c36e727709d45e5a66
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989267"
---
# <a name="step-1-create-and-deploy-common-header-and-acknowledgment-schemas"></a>手順 1: を作成し、一般的なヘッダーと確認スキーマをデプロイします。
メッセージ インスタンスのヘッダー (MSH セグメント) を検証するのにには、ヘッダー スキーマを使用します。 受信確認メッセージのインスタンスを生成するのにには、受信確認スキーマを使用します。 このプロセスは、HL7 スキーマのすべてのバージョン間で共通です。  
  
### <a name="to-create-the-header-and-acknowledgment-schemas"></a>ヘッダーと受信確認スキーマを作成するには  
  
1. 開始**Microsoft Visual Studio 2012**します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], の **ファイル** メニューをポイント **新規**, 、クリックして **プロジェクト**します。  
  
3. 新しいプロジェクト] ダイアログ ボックスで、**プロジェクトの種類**一覧で、展開**BizTalk プロジェクト**、し、[ **BTAHL7Projects**します。  
  
4. **テンプレート**一覧で、 **BTAHL7V2XCommon プロジェクト**します。  
  
5. **名前**フィールドに「 **Interrogative_2XSchemas**、順にクリックします**OK**します。  
  
    ソリューション エクスプ ローラーでは、(ACK_24_GLO_DEF.xsd、ACK_25_GLO_DEF.xsd、および MSH_25_GLO_DEF.xsd) の 3 つのスキーマをプロジェクトに含まれることに注意してください。  
  
    Visual Studio は開いたままにしておきます。  
  
## <a name="step-1a-assign-a-strong-key-to-the-assembly-and-deploy"></a>手順 1 a: アセンブリに厳密なキーを割り当てるとデプロイ  
 アセンブリに厳密なキーを割り当てるし、アセンブリを配置するには、次の手順を使用します。  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a>強力なキーを割り当てるし、アセンブリを展開するには  
  
1. 開始**Visual Studio 2012 のコマンド プロンプト**します。  
  
2. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトで、ディレクトリの変更、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative のアクセラレータチュートリアル フォルダーです。  
  
3. コマンド プロンプトで「 **sn – k key.snk**、押します **」と入力**します。 成功メッセージが出力ウィンドウに表示されることを確認します。  
  
   > [!NOTE]
   >  適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アセンブリのトラブルシューティングを行う。  
  
4. ソリューション エクスプ ローラーで右クリックして**Interrogative_2XSchemas**プロジェクトをクリックして**プロパティ**します。  
  
5. Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**します。  
  
6. 右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンを順にクリックします。  
  
7. アセンブリ キー ファイル ダイアログ ボックスを参照\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\Interrogative チュートリアルでは、アクセラレータをクリックします**key.snk**、 をクリックし、**オープン**します。  
  
8. Interrogative_2XSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**変更を保存します。  
  
9. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、ソリューション エクスプ ローラーで右クリック**Interrogative_2XSchemas**プロジェクトをクリックして**デプロイ**します。 成功メッセージが出力ウィンドウに表示を確認します。  
  
   > [!NOTE]
   >  デプロイの適切なメッセージが表示されない場合は、使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]デプロイのトラブルシューティングを行う。  
  
   進みます[手順 2: V2.4 の一般的なスキーマを作成する](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)します。