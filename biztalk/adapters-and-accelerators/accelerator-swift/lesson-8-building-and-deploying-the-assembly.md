---
title: "レッスン 8: のビルドと、アセンブリの展開 |Microsoft ドキュメント"
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
ms.assetid: 74c9dfbd-8365-4600-8885-a9d9c3490dd5
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6f043764dba966d662274d47643e01bec3735a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-8-building-and-deploying-the-assembly"></a>レッスン 8: のビルドと、アセンブリの展開
このレッスンでは、ビルドし、前の手順で作成したパイプラインを含むアセンブリを生成するパイプライン プロジェクトを配置します。 このレッスンは、これまでに作成した作業ではコンパイル エラーがないようにします。  
  
 保存して、プロジェクトをコンパイルしてアセンブリ (DLL) ファイル、 \<*ドライブ*>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\bin\Development フォルダーです。  
  
### <a name="to-build-and-deploy-the-project"></a>プロジェクトをビルドして展開するには  
  
1.  ソリューション エクスプ ローラーで右クリック**SWIFTPipelines**、クリックして**ビルド**です。  
  
    > [!NOTE]
    >  コンパイル プロセス中に表示しないようにすべてのエラーです。 場合は、エラーの原因を確認して修正して、プロジェクトを再構築します。 A4SWIFT のパイプライン コンポーネントに関連する警告の数を参照してください、ただし、します。 これらの警告を設定して、引き起こす状況を修正することができます、**ローカル コピー** 、パイプライン コンポーネントへの参照のプロパティ**False**です。 詳細についてを参照してください「パイプライン プロジェクトをビルドすることがありますで警告を表示」[その他の既知の問題](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)です。  
  
2.  SWIFTPipelines.dll の作成を検証するファイルを使用して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]エクスプ ローラーで、[参照] \<*ドライブ*: > \labs\SWIFTProject\SWIFTPipelines\bin\Development、このフォルダーにファイルが存在することを確認してください。  
  
3.  ソリューション エクスプ ローラーで右クリック**SWIFTPipelines**、クリックして**展開**です。  
  
    > [!NOTE]
    >  展開プロセス中に表示しないようにエラーまたは警告があります。 作成する場合は、エラーの原因を確認して、して修正し、プロジェクトを再展開します。  
  
4.  展開の成功を準拠するように、**ビュー**のメニュー[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]をクリックして**BizTalk エクスプ ローラー**です。  
  
5.  右クリック**BizTalk 構成データベース**、クリックして**更新**です。  
  
6.  展開、**アセンブリ**ノード アクセラレータが正常に展開されたことを確認および**SWIFTPipelines (1.0.0.0)**です。  
  
 進みます[第 4 章: 受信 XML を作成して、フラット ファイル送信ポート](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md)です。