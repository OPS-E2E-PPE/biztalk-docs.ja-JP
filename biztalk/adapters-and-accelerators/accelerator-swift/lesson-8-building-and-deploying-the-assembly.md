---
title: 'レッスン 8: 構築と、アセンブリの配置 |Microsoft Docs'
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
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80e97076bb503d51bd2180c3f4bea950c0c04a46
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968387"
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a>レッスン 8: 構築と、アセンブリの配置
このレッスンでは、ビルドし、前の手順で作成したパイプラインを含むアセンブリを生成するパイプライン プロジェクトを配置します。 このレッスンでは、これまでに作成した作業でコンパイル エラーがないをによりします。  
  
 保存して、プロジェクトをコンパイルしてアセンブリ (DLL) ファイル、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development フォルダー。  
  
### <a name="to-build-and-deploy-the-project"></a>プロジェクトをビルドして展開するには  
  
1. ソリューション エクスプ ローラーで右クリックして**SWIFTPipelines**、 をクリックし、**ビルド**します。  
  
   > [!NOTE]
   >  コンパイル プロセス中にいない、エラーが発生する必要があります。 場合は、エラーの原因を確認、修正およびプロジェクトを再ビルドします。 ただし、A4SWIFT パイプライン コンポーネントに関連する警告の番号が表示、可能性があります。 設定して、これらの警告につながる条件を修正することができます、**ローカル コピー**パイプライン コンポーネントの参照のプロパティ**False**します。 詳細についてを参照してください「で警告結果がパイプライン プロジェクトのビルド」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)します。  
  
2. SWIFTPipelines.dll の作成を検証するファイルを使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、参照\<*ドライブ*:\>\labs\SWIFTProject\SWIFTPipelines\bin\Development でファイルが存在することを確認してくださいこのフォルダーです。  
  
3. ソリューション エクスプ ローラーで右クリックして**SWIFTPipelines**、 をクリックし、**デプロイ**します。  
  
   > [!NOTE]
   >  展開プロセス中にエラーまたは警告しない表示されます。 場合は、エラーの原因を確認、修正、およびプロジェクトを再デプロイします。  
  
4. デプロイの成功に準拠するように、**ビュー**のメニュー [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、 をクリックして**BizTalk エクスプ ローラー**します。  
  
5. 右クリック**BizTalk 構成データベース**、 をクリックし、**更新**します。  
  
6. 展開、**アセンブリ**ノード、アクセラレータが正常にデプロイされることを確認します。 **SWIFTPipelines (1.0.0.0)** します。  
  
   進みます[モジュール 4: 受信 XML を作成し、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)します。