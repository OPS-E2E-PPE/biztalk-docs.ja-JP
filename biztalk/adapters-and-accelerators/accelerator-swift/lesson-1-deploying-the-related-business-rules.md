---
title: 'レッスン 1: 関連するビジネス ルールの展開 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, deploying
- deploying, business rules
ms.assetid: f8f5b103-4b66-4836-8165-99692574961a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6228f890e0f508650827f2bb2c3e52b5d29f96f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971107"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a>レッスン 1: 関連するビジネス ルールの展開
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で、A4SWIFT ソフトウェア開発キット (SDK)、ビジネス ルール エンジン (BRE) の展開ユーティリティと呼ばれるプログラムが含まれています。 このレッスンでは、このユーティリティを使用して展開されたスキーマのアセンブリを検査、必要なルールを決定および必要なボキャブラリとすべてのスキーマのポリシーを展開します。  
  
 必要なルールを識別し、ビジネス ルール作成ツールを使用して、ボキャブラリとポリシーを展開する SWIFT 標準リリース ガイド (SRG) を使用して規則をデプロイすることもできます。  
  
### <a name="to-deploy-the-related-business-rules"></a>関連するビジネス ルールを展開するには  
  
1. をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for SWIFT**をクリックして**BRE 配置ユーティリティ**します。  
  
2. BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**します。  
  
3. .NET グローバル アセンブリ キャッシュ ダイアログ ボックスで、 **SWIFTSchemas**、 をクリックし、 **OK**。  
  
   > [!NOTE]
   >  アセンブリを参照 SWIFTSchemas 以前に展開します。  
  
4. クリックして**デプロイ**します。  
  
    そのアセンブリを展開するスキーマに基づき、配置ユーティリティは、関連するルールを識別し、BRE を使用して発行します。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。  
  
    **デプロイが完了しました。詳細については、ログ ファイルまたはビジネス ルール作成ツールを表示します。**  
  
5. SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。  
  
6. Windows エクスプ ローラーを参照\<*ドライブ*\>: \Documents and ことを確認する場合のバックアップ データ、ログ ファイル**BREDeploymentLog.txt**に表示されます、フォルダー。  
  
   > [!NOTE]
   >  各展開の手順を確認するテキスト エディターを使用してログ ファイルを開くことができます。  
  
7. ルール エンジン更新サービスを再起動します。 クリックして**開始**、**実行**入力、 **services.msc**、 をクリック**ok**。 **サービス (ローカル)** ウィンドウで、右クリックして**ルール エンジン更新サービス**、順にクリックします**再起動**します。  
  
   進みます[レッスン 2: ビジネス ルールの作成ツールを使用して、展開を確認する](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)します。