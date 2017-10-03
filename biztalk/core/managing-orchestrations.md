---
title: "オーケストレーションの管理 |Microsoft ドキュメント"
description: "BizTalk server の開始を含むオーケストレーションを使用、停止、バインド、構成、追跡を有効にする、中断へのリンクと詳細"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2553eec3-b863-45fb-90af-7eddcfa7add7
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18cd12c202822c4d9ff849cc762b55e8f4880d80
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-orchestrations"></a>オーケストレーションを管理します。

## <a name="overview"></a>概要
ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使ってオーケストレーションを管理する方法について説明します。 オーケストレーションとは、実行可能なビジネス プロセスのことです。 オーケストレーションの背景については、次を参照してください。[オーケストレーション](../core/orchestrations.md)です。  

## <a name="add-to-application"></a>アプリケーションに追加します。  
 オーケストレーションは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。 オーケストレーションを個別にアプリケーションへ追加することはできません。オーケストレーションは次のようにしてアプリケーションに追加されます。  
  
-   」の説明に従って、アプリケーションにオーケストレーションを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。  
  
-   」の説明に従って、オーケストレーションを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
-   開発者が展開したときに、アプリケーションからオーケストレーションを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  

## <a name="biztalk-administration-tasks"></a>BizTalk 管理コンソール タスク  
 管理コンソールでは、次のアクションを実行できます。  
  
-   オーケストレーションのバインドを構成 (つまり、オーケストレーションを適切な送信/受信ポートおよびホストにバインド) したり、これらのバインドをオーケストレーションから削除する。  
  
-   オーケストレーションのメッセージ追跡を構成する。  
  
-   オーケストレーションのインスタンス情報を表示する。  
  
-   オーケストレーションを適切なホストに参加させる/オーケストレーションをホストから参加解除する。  
  
-   オーケストレーションによるメッセージの処理を開始/中止する。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
> [!NOTE]
>  開発者は、デザイナーを使用するオーケストレーション、オーケストレーションを作成する」の説明に従って[オーケストレーション デザイナーを使用してオーケストレーションを作成する](../core/creating-orchestrations-using-orchestration-designer.md)です。 開発者は、このセクションで説明する管理コンソールを使用して、開発プロセス中にオーケストレーションを管理できます。  
  
## <a name="next-steps"></a>次の手順
  
-   [オーケストレーションのバインドを構成します。](../core/how-to-configure-bindings-for-an-orchestration.md)  
  
-   [オーケストレーションをバインド解除します。](../core/how-to-unbind-an-orchestration.md)  
  
-   [オーケストレーションの追跡を構成します。](../core/how-to-configure-tracking-for-an-orchestration.md)  
  
-   [オーケストレーションのインスタンス情報の表示](../core/how-to-view-instance-information-for-an-orchestration.md)  
  
-   [オーケストレーションをアプリケーションから削除します。](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [オーケストレーションを参加させる](../core/how-to-enlist-an-orchestration.md)  
  
-   [オーケストレーションを参加解除します。](../core/how-to-unenlist-an-orchestration.md)  
  
-   [オーケストレーションを開始します。](../core/how-to-start-an-orchestration.md)  
  
-   [オーケストレーションを停止します。](../core/how-to-stop-an-orchestration.md)  
  
-   [中断、再開、およびオーケストレーション インスタンスの終了](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)  
  
-   [オーケストレーションをアップグレードします。](../core/how-to-upgrade-an-orchestration.md)