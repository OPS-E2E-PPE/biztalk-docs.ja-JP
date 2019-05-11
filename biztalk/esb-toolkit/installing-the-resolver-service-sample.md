---
title: リゾルバー サービス サンプルをインストールする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88168abccba2fc8eb266816b6820bbcdc72d0c67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249734"
---
# <a name="installing-the-resolver-service-sample"></a>リゾルバー サービス サンプルをインストールします。
このセクションでは、リゾルバー サービス サンプルをインストールするプロセスについて説明します。 リゾルバー サービスに依存して、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]ソリューションのコアします。 インストール、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core は自動的にコピーして、適切な場所には、このサンプルに必要なコア アセンブリをインストールします。  
  
 **ソリューションのプロジェクトからリゾルバー サービス サンプルをインストールするには**  
  
1.  Windows エクスプ ローラーで、\Source\Samples\ResolverService\Install\Scripts フォルダーを開きます。  
  
2.  Setup_bin.cmd ファイルをダブルクリックします。  
  
3.  サンプルでは、正常にインストールすることを確認するか、アプリケーションを実行するときに問題が発生する場合、必要なアセンブリおよびその他の成果物の有無を確認する次の表で指定された一覧を使用することができます。  
  
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
|%Program Files %\\BizTalk Server\Pipeline コンポーネント|パイプライン コンポーネント|(なし)|