---
title: "Visual Studio での MSBUILD の統合 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4a639945881625dd697798080c913ec0e5e3a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msbuild-integration-with-visual-studio"></a>MSBUILD の Visual Studio との統合
Visual Studio では MSBUILD プロジェクト ファイル形式を使用して、BizTalk プロジェクトなどのマネージ プロジェクトに関するビルド情報を保存します。 Visual Studio から追加および変更されたプロジェクト設定は、プロジェクトごとに生成される .btproj ファイルに反映されます。 Visual Studio は、MSBUILD のホストされたインスタンスを使用して BizTalk プロジェクトをビルドします。つまり、BizTalk プロジェクトは Visual Studio でビルドすることも、コマンド ラインからビルドすることもできます。結果はどちらも同じです。  
  
 MSBUILD の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)です。  
  
 次の手順は、MSBUILD を使用してサンプル BizTalk プロジェクトをコマンド ラインからビルドする方法を示しています。  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a>BizTalk プロジェクトをコマンド ラインからビルドするには  
  
1.  開始**Visual Studio コマンド プロンプト**です。  
  
2.  プロジェクト ディレクトリに切り替えて、MSBUILD コマンドを実行して BizTalk ソリューションを構築します。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  ソリューションには、BizTalk プロジェクトおよび C# クラス ライブラリなどの非 BizTalk プロジェクトを含むことができます。