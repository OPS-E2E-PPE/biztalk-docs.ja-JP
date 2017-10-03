---
title: "レッスン 4: のビルドと、アセンブリの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5521b5921dbfcc3c8a3c5916fc4d4a2dc96eebbd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a>レッスン 4: のビルドと、アセンブリの展開
このレッスンでは、ビルドし、前のレッスンで作成したスキーマを含むアセンブリを生成するプロジェクトを配置します。 このタスクにより、これまでに作成した作業ではコンパイル エラーがないです。  
  
 アセンブリを展開する構成データベースにアセンブリのコピーを格納し、グローバル アセンブリ キャッシュ (GAC) にインストールします。 次の手順では、ソリューション エクスプ ローラーから直接展開します。  
  
 アセンブリ (DLL ファイル) に、プロジェクトがコンパイル時に[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で DLL を保存、 \<*ドライブ*>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for SWIFT\bin\プロジェクト フォルダー内のフォルダーを開発します。  
  
### <a name="to-build-and-deploy-the-project"></a>プロジェクトをビルドして展開するには  
  
1.  ソリューション エクスプ ローラーで右クリック**SWIFTSchemas**、クリックして**ビルド**です。  
  
    > [!NOTE]
    >  いることを確認**ビルドに成功した**画面の左下隅に表示されます。 コンパイル時に、一部のステータス メッセージを参照してください可能性があります。 SWIFT のスキーマを処理する場合、これらのメッセージは正常です。 すべてのエラーが表示されない場合は、ツールをクリックし、[BizTalk Server 管理を開くには、BizTalk Server 管理コンソール] をクリックします。 BizTalk 管理コンソールで、イベント ビューアーと正常性と動作状況の追跡 (HAT) 機能を使用して、、エラーを修正して再構築します。  
  
2.  使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、   **\<*ドライブ*>: \labs\SWIFTProject\SWIFTSchemas\bin\Development** フォルダーのことを確認し、 **SWIFTSchemas.dll**このフォルダーにファイルが存在します。  
  
3.  ソリューション エクスプ ローラーで右クリック**SWIFTSchemas**、クリックして**展開**です。  
  
    > [!NOTE]
    >  いることを確認**配置正常終了**画面の左下隅に表示されます。  
  
### <a name="to-confirm-deployment-success"></a>展開の成功を確認するには  
  
1.  をクリックして**ビュー**  をクリックし、 **BizTalk エクスプ ローラー**です。  
  
2.  展開、**アセンブリ**ノードいることを確認および**SWIFTSchemas (1.0.0.0)**一覧に表示されます。  
  
     SWIFTSchemas が一覧に表示された場合、アセンブリが正常に展開されていると参照および使用できるを他の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  
  
 進みます[第 3 章: パイプライン プロジェクトを追加する](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)です。