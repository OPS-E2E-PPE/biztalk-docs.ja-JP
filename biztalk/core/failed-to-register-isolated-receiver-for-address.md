---
title: 分離受信場所のアドレスを登録できませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 313b436a-d7c5-4b46-bfe3-bbad0d8efe42
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edd55360a1638128ed687cf83f2e05bf52ad9dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246026"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a>アドレスの分離受信場所を登録できませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|アドレス "{0}" の分離受信場所を登録できませんでした。受信場所が存在しないか、無効になっています。|  
  
## <a name="explanation"></a>説明  
 このエラーは、公開された WCF 分離受信場所に対応する受信場所が見つからなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、次の操作: BizTalk 管理コンソールで、BizTalk WCF サービス公開ウィザード生成が存在し、ある Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認してください開始しました。  
  
 受信場所の作成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [発行の WCF サービスを分離 WCF 受信アダプター](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: Wcf-basichttp アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)