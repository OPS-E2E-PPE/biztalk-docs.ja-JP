---
title: 見つかりませんメタデータの受信場所 |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c397fb5-f400-4cff-85b9-5bf0d2069557
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eb45272f7d3ef4491b59d5b019eb4499bcf5dff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268978"
---
# <a name="receive-location-for-metadata-not-found"></a>メタデータの受信場所が見つかりません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|メタデータの受信場所 "{0}" が見つかりません  (Web.config の受信場所マッピングを確認して、この受信場所が存在するか確認してください)。|  
  
## <a name="explanation"></a>説明  
 このエラーは、公開された WCF 分離受信場所に、メタデータの対応する受信場所が見つからなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、次の操作: BizTalk 管理コンソールで、BizTalk WCF 公開ウィザードによって生成されたが存在し、開始、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認してください。  
  
 受信場所の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [WCF サービスの公開](../core/publishing-wcf-services.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: Wcf-netmsmq アダプタを使用して WCF サービスの発行](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)