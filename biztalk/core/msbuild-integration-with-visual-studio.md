---
title: MSBUILD と Visual Studio の統合 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aedcabf7-b2cf-482a-9ade-7311e104bff9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01b0f59d73c48dba994b0c57cae3b4c697e426b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264539"
---
# <a name="msbuild-integration-with-visual-studio"></a>MSBUILD の Visual Studio との統合
Visual Studio では MSBUILD プロジェクト ファイル形式を使用して、BizTalk プロジェクトなどのマネージド プロジェクトに関するビルド情報を保存します。 プロジェクトごとに生成される .btproj ファイルには、プロジェクトの設定を追加して、Visual Studio を使用して変更が反映されます。 Visual Studio では、MSBUILD のホスト インスタンスを使用して、BizTalk プロジェクトでは、構築、つまりまたは同一の結果をコマンドラインから Visual Studio で BizTalk プロジェクトを構築できます。  
  
 MSBUILD の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=193567](http://go.microsoft.com/fwlink/?LinkId=193567)します。  
  
 次の手順では、MSBUILD を使用してコマンドラインからサンプル BizTalk プロジェクトをビルドする方法を示します。  
  
## <a name="to-build-a-biztalk-project-from-a-command-line"></a>コマンドラインからの BizTalk プロジェクトをビルドするには  
  
1.  開始**Visual Studio コマンド プロンプト**します。  
  
2.  プロジェクト ディレクトリに切り替えるし、BizTalk ソリューションをビルドする MSBUILD コマンドを実行します。  
  
    ```  
    msbuild unittesttest.sln /p:Configuration=Debug  
    ```  
  
    > [!NOTE]
    >  ソリューションがなど、BizTalk、および BizTalk 以外のプロジェクトを含めることができます、C#クラス ライブラリ。