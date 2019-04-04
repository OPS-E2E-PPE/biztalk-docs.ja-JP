---
title: オーケストレーションの管理 |Microsoft Docs
description: BizTalk server の開始を含むオーケストレーションを使用、停止、バインド、構成、追跡を有効にする、中断へのリンクと詳細
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a989cb7853e63e1e603febf44db45288276ecd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976483"
---
# <a name="manage-orchestrations"></a>オーケストレーションを管理します。

## <a name="overview"></a>概要
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使ってオーケストレーションを管理する方法について説明します。 オーケストレーションとは、実行可能なビジネス プロセスのことです。 オーケストレーションの背景については、[オーケストレーション](../core/orchestrations.md)を参照してください。  

## <a name="add-to-application"></a>アプリケーションに追加します。  
 オーケストレーションは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。 オーケストレーションを個別にアプリケーションへ追加することはできません。オーケストレーションは次のようにしてアプリケーションに追加されます。  
  
- 」の説明に従って、アプリケーションにオーケストレーションを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
- 」の説明に従って、オーケストレーションを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。  
  
- 開発者が展開したときに、アプリケーションから、オーケストレーションを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  

## <a name="biztalk-administration-tasks"></a>BizTalk 管理コンソール タスク  
 管理コンソールでは、次のアクションを実行できます。  
  
-   オーケストレーションのバインドを構成 (つまり、オーケストレーションを適切な送信/受信ポートおよびホストにバインド) したり、これらのバインドをオーケストレーションから削除する。  
  
-   オーケストレーションのメッセージ追跡を構成する。  
  
-   オーケストレーションのインスタンス情報を表示する。  
  
-   オーケストレーションを適切なホストに参加させる/オーケストレーションをホストから参加解除する。  
  
-   オーケストレーションによるメッセージの処理を開始/中止する。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]を参照してください。 
> 
> [!NOTE]
>  開発者は、」の説明に従って、オーケストレーションを作成するオーケストレーション デザイナーを使用[オーケストレーション デザイナーを使用してオーケストレーションを作成](../core/creating-orchestrations-using-orchestration-designer.md)です。 開発者は、このセクションで説明する管理コンソールを使用して、開発プロセス中にオーケストレーションを管理できます。  
  
## <a name="next-steps"></a>次のステップ
  
-   [オーケストレーションのバインドの構成](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [オーケストレーションのバインド解除](../core/how-to-unbind-an-orchestration.md)  
  
-   [オーケストレーションの追跡を構成する](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [オーケストレーションのインスタンス情報を表示する](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [オーケストレーションをアプリケーションから削除する](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [オーケストレーションの登録](../core/how-to-enlist-an-orchestration.md)  
  
-   [オーケストレーションの登録解除](../core/how-to-unenlist-an-orchestration.md)  
  
-   [オーケストレーションの開始](../core/how-to-start-an-orchestration.md)  
  
-   [オーケストレーションの停止](../core/how-to-stop-an-orchestration.md)  
  
-   [オーケストレーション インスタンスの中断、再開、および終了](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [オーケストレーションのアップグレード](../core/how-to-upgrade-an-orchestration.md)