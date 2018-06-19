---
title: パイプラインの管理 |Microsoft ドキュメント
description: 追跡や送信ポートのパイプライン プロパティを有効にするにまたは BizTalk Server で受信場所へのクイック リンク
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
ms.openlocfilehash: 0edfbdd97e134abc6f153acf136ff62a979f8b0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262538"
---
# <a name="managing-pipelines"></a>パイプラインの管理

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールを使用して BizTalk グループのパイプラインを管理する方法について説明します。 特定の送信ポートまたは受信場所のパイプライン プロパティの構成に加え、イベントおよびメッセージの追跡を構成することができます。  
  
 パイプラインでは、受信メッセージおよび送信メッセージに対して、ネイティブ形式から XML への変換、データの暗号化や復号化、プロパティの昇格などの操作を行います。  
  
 パイプラインを単独でアプリケーションに追加することはできません。パイプラインは次のようにしてアプリケーションに追加されます。  
  
-   」の説明に従って、アプリケーションに、パイプラインを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。  
  
-   」の説明に従って、パイプラインを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
-   開発者が展開したときのアプリケーションに、Visual Studio からパイプラインを含むアセンブリ」の説明に従って[BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。  
  
 パイプラインに関する背景情報については、次を参照してください。[パイプライン](../core/pipelines.md)です。 パイプラインの開発方法の詳細については、次を参照してください。[パイプライン デザイナーを使用してパイプラインを作成する](../core/creating-pipelines-using-pipeline-designer.md)です。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="next-steps"></a>次の手順
  
-   [パイプラインの追跡を構成します。](../core/how-to-configure-tracking-for-a-pipeline.md)  
  
-   [送信ポートのインスタンスごとにパイプライン プロパティを構成します。](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)  
  
-   [インスタンスごとのパイプライン プロパティを構成する受信場所](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)