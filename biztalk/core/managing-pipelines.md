---
title: パイプラインを管理する |Microsoft Docs
description: 追跡や送信ポートのパイプライン プロパティを有効にするか、BizTalk Server で受信場所へのクイック リンク
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60b54e0-0a5a-4264-b0e5-96bb187d782b
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b15931468b5ba3bf43f227563dd270aabbfa29b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995259"
---
# <a name="managing-pipelines"></a>パイプラインの管理

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールを使用して BizTalk グループのパイプラインを管理する方法について説明します。 特定の送信ポートまたは受信場所のパイプライン プロパティの構成に加え、イベントおよびメッセージの追跡を構成することができます。  
  
 パイプラインでは、受信メッセージおよび送信メッセージに対して、ネイティブ形式から XML への変換、データの暗号化や復号化、プロパティの昇格などの操作を行います。  
  
 パイプラインを単独でアプリケーションに追加することはできません。パイプラインは次のようにしてアプリケーションに追加されます。  
  
- 」の説明に従って、アプリケーションに、パイプラインを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。  
  
- 」の説明に従って、パイプラインを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。  
  
- 開発者が展開したとき、アプリケーションに、Visual Studio からのパイプラインを含むアセンブリで説明されている[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。  
  
  パイプラインに関する背景情報は、次を参照してください。[パイプライン](../core/pipelines.md)します。 パイプラインの開発方法の詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成](../core/creating-pipelines-using-pipeline-designer.md)です。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="next-steps"></a>次のステップ
  
-   [パイプラインの追跡を構成する](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [送信ポートのインスタンスごとにパイプライン プロパティを構成する](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [受信場所のインスタンスごとにパイプライン プロパティを構成する](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)