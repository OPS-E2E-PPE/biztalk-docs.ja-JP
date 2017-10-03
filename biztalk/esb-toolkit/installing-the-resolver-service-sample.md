---
title: "リゾルバー サービスのサンプルをインストールする |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b06c7383dee805612a3f599148f1d631891ace79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-the-resolver-service-sample"></a>リゾルバー サービスのサンプルをインストールします。
このセクションでは、リゾルバー サービスのサンプルをインストールするプロセスについて説明します。 リゾルバー サービスに依存して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コア ソリューションです。 インストール、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コアは自動的にコピーして、適切な場所にこのサンプルに必要な中核となるアセンブリをインストールします。  
  
 **ソリューションのプロジェクトからリゾルバー サービスのサンプルをインストールするには**  
  
1.  Windows エクスプローラで、\Source\Samples\ResolverService\Install\Scripts フォルダーを開きます。  
  
2.  Setup_bin.cmd ファイルをダブルクリックします。  
  
3.  このサンプルのインストールの成功を確認するまたはアプリケーションを実行するときに問題が発生する場合、必要なアセンブリとその他のアイテムの存在をチェックする次の表に用意された一覧を使用できます。  
  
|場所|カテゴリ|コンポーネントの名前とバージョン|  
|--------------|--------------|---------------------------------------|  
|BizTalk アプリケーション GlobalBank.ESB|オーケストレーション|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|送信ポート|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|受信ポート|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|受信場所|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|スキーマ|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|パイプライン|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|リソース|(なし)|  
|BizTalk アプリケーション GlobalBank.ESB|ポリシー|ResolveEndpoint|  
|||ResolveMap|  
|BizTalk アプリケーション GlobalBank.ESB|マップ|(なし)|  
|グローバル アセンブリ キャッシュ|アセンブリ|(なし)|  
|%Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline コンポーネント|パイプライン コンポーネント|(なし)|