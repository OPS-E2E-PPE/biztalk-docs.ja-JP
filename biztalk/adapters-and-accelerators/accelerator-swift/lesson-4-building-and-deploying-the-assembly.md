---
title: レッスン 4:ビルドと、アセンブリの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- building assemblies
- deploying, assemblies
- assemblies, building
- assemblies, deploying
ms.assetid: 58397c35-6048-4ac9-a8b8-a528dd1cb82a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d180180f178defe4fc4d93de36fb8ac8f6ed88a0
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530298"
---
# <a name="lesson-4-building-and-deploying-the-assembly"></a>レッスン 4:構築およびアセンブリを展開します。
このレッスンでは、ビルドし、前のレッスンで作成したスキーマを含むアセンブリを生成するプロジェクトを配置します。 このタスクにより、これまでに作成した作業でコンパイル エラーがないです。  
  
 アセンブリを展開する構成データベースにアセンブリのコピーを格納し、そのグローバル アセンブリ キャッシュ (GAC) にインストールします。 次の手順では、ソリューション エクスプ ローラーから直接デプロイします。  
  
 アセンブリ (DLL ファイル) に、プロジェクトのコンパイル時に Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]で DLL を保存、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk Accelerator for SWIFT\bin\プロジェクト フォルダー内のフォルダーを開発します。  
  
### <a name="to-build-and-deploy-the-project"></a>プロジェクトをビルドして展開するには  
  
1. ソリューション エクスプ ローラーで右クリックして**SWIFTSchemas**、 をクリックし、**ビルド**します。  
  
   > [!NOTE]
   >  いることを確認**ビルドが成功しました**画面の左下隅に表示されます。 コンパイル プロセス中には、一部のステータス メッセージを参照してください可能性があります。 SWIFT スキーマを処理するとき、これらのメッセージは正常です。 すべてのエラーが表示されない場合は、ツールをクリックし、し、[BizTalk Server の管理を BizTalk Server 管理コンソールを開く] をクリックします。 BizTalk 管理コンソールで、イベント ビューアーと正常性と動作状況の追跡 (HAT) 機能を使用して、、エラーを修正して再構築します。  
  
2. 使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照、  **\<*ドライブ*\>: \labs\SWIFTProject\SWIFTSchemas\bin\Development**フォルダー、いることを確認し、 **SWIFTSchemas.dll**このフォルダーにファイルが存在します。  
  
3. ソリューション エクスプ ローラーで右クリックして**SWIFTSchemas**、 をクリックし、**デプロイ**します。  
  
   > [!NOTE]
   >  いることを確認**配置正常終了**画面の左下隅に表示されます。  
  
### <a name="to-confirm-deployment-success"></a>展開の成功を確認するには  
  
1. クリックして**ビュー**  をクリックし、 **BizTalk エクスプ ローラー**します。  
  
2. 展開、**アセンブリ**ノードことを確認します**SWIFTSchemas (1.0.0.0)** 一覧に表示されます。  
  
    SWIFTSchemas が一覧に表示された場合、アセンブリが正常に展開されていると参照および使用できる他の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクト。  
  
   続行する[モジュール 3。パイプライン プロジェクトの追加](../../adapters-and-accelerators/accelerator-swift/module-3-adding-a-pipeline-project.md)します。