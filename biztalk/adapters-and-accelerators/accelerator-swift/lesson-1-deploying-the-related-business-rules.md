---
title: 'レッスン 1: 関連するビジネス ルールの展開 |Microsoft ドキュメント'
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
ms.openlocfilehash: 17c4b470b802a980306481361c1fafcec4f70269
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960768"
---
# <a name="lesson-1-deploying-the-related-business-rules"></a>レッスン 1: 関連するビジネス ルールの展開
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で、A4SWIFT ソフトウェア開発キット (SDK)、ビジネス ルール エンジン (BRE) の展開ユーティリティと呼ばれるプログラムが含まれています。 このレッスンでは、このユーティリティを使用して展開されたスキーマのアセンブリを調べる、必須のルールを決定および必要なボキャブラリとすべてのスキーマのポリシーを展開します。  
  
 必要なルールを識別し、ビジネス ルール作成ツールを使用して、ボキャブラリとポリシーを展開する SWIFT 標準リリース ガイド (SRG) を使用して規則を展開することもできます。  
  
### <a name="to-deploy-the-related-business-rules"></a>関連するビジネス ルールを展開するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 SWIFT**をクリックして**BRE 配置ユーティリティ**です。  
  
2.  BRE 配置ユーティリティ] ダイアログ ボックスで、[**参照**です。  
  
3.  .NET グローバル アセンブリ キャッシュ] ダイアログ ボックスで、[ **SWIFTSchemas**、順にクリック**OK**です。  
  
    > [!NOTE]
    >  SWIFTSchemas とは、アセンブリが以前に展開します。  
  
4.  をクリックして**展開**です。  
  
     そのアセンブリと共に配置するスキーマに基づいて、配置ユーティリティは関連するルールを識別し、BRE で使用するためを公開します。 完了したら、BRE 配置ユーティリティが表示されます、次のメッセージ。  
  
     **展開が完了しました。詳細については、ログ ファイルまたはビジネス ルール作成ツールを表示します。**  
  
5.  SWIFT BRE 配置ユーティリティ ダイアログ ボックスを閉じます。  
  
6.  Windows エクスプ ローラーで参照\<*ドライブ*\>: \Documents and settings \all \all データいることを確認、ログ ファイル**BREDeploymentLog.txt**に表示されます、フォルダーです。  
  
    > [!NOTE]
    >  各展開の手順を確認するテキスト エディターを使用してログ ファイルを開くことができます。  
  
7.  ルール エンジン更新サービスを再起動します。 クリックして**開始**をクリックすると、**実行**入力、 **services.msc**をクリックすると、 **[ok]** です。 **サービス (ローカル)** ウィンドウを右クリックして**ルール エンジン更新サービス**、クリックして**再起動**です。  
  
 進みます[レッスン 2: ビジネス ルール作成ツールを使用して、展開を確認する](../../adapters-and-accelerators/accelerator-swift/lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool.md)です。