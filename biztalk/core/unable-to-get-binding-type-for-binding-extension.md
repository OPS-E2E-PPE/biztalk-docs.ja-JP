---
title: バインド拡張機能のバインドの種類を取得できません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7cfc81-7439-48f9-8cac-42b2419ecd9d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79b649f69b7503f345f212aa5f014ce7b256148d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973768"
---
# <a name="unable-to-get-binding-type-for-binding-extension"></a>バインド拡張機能のバインドの種類を取得できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|バインド拡張機能 "{0}" のバインドの種類を取得できません。 アプリケーションが開いている状態のときに machine.config が更新された場合は、アプリケーションを再起動して変更を反映してください。 machine.config にこのバインド拡張機能が登録されているか確認してください。|  
  
## <a name="explanation"></a>説明  
 WCF-Custom または WCF-CustomIsolated トランスポートのカスタム バインディング拡張機能が適切に構成されませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 解決するのには、このエラーは、次の 1 つ以上を実行します。  
  
-   確認、 **machine.config ファイル**で **%WinDir%\Microsoft.NET\Framework\v4.0.30319\Config**が、 \< **bindingExtensions** \>要素が適切に構成します。  
  
-   Windows エクスプ ローラーに移動 **%WinDir%\Assembly**、カスタム バインディングの拡張機能を実装するアセンブリが正しくインストールされているかどうかを確認します。  
  
-   WCF-Custom アダプターの場合、BizTalk 管理コンソールで、WCF トランスポートを実行するホスト インスタンスを再起動します。  
  
-   WCF-CustomIsolated アダプターの場合、IIS 管理コンソールで、WCF トランスポートをホストするアプリケーション プールを再起動します。  
  
-   BizTalk 管理コンソールを開いていた場合は、閉じてから開きます  
  
 詳細については、次のリソースを参照してください。  
  
-   [WCF アダプターで WCF 機能拡張ポイントを有効にする方法](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)