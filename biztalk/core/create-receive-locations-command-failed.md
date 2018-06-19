---
title: 作成する受信場所のコマンドが失敗した |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f73ff211-af7f-40be-ad7e-7bde7bf75a2d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a6ad1c7992bb696eb05223e9830a7114d8a0fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238034"
---
# <a name="create-receive-locations-command-failed"></a>受信場所の作成コマンドが失敗しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|作成する受信場所のコマンドが失敗しました: ファイル名 = {0} 引数 = \  ExitCode = \ {2 \}|  
  
## <a name="explanation"></a>説明  
 公開ウィザードが受信場所の作成に失敗しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、次の操作: BizTalk 管理コンソールで、BizTalk WCF 公開ウィザードによって生成されたが存在し、開始、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認してください。  
  
 受信場所の作成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [発行の WCF サービスを分離 WCF 受信アダプター](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)