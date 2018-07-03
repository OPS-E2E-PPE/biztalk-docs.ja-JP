---
title: 受信場所のアドレスが見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 637f3925-06ff-47b2-99db-f85e829ee318
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55b3744f6590ee706bcc3df4124f964306634ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994947"
---
# <a name="receive-location-for-address-not-found"></a>アドレスの受信場所が見つかりません
## <a name="details"></a>詳細  
  
|                 |                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------|
|  製品名   |      [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| 製品バージョン |                  [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    イベント ID     |                                               0                                               |
|  イベント ソース   |                                               0                                               |
|    コンポーネント    |                                               0                                               |
|  シンボル名  |                                               0                                               |
|  メッセージ テキスト   | アドレスの受信場所"{0}"が見つかりませんでした。 (BizTalk 受信場所が無効になっている可能性があります)。 |
  
## <a name="explanation"></a>説明  
 このエラーは、公開された WCF 分離受信場所に対応する受信場所が見つからなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、次の操作: BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されていることを確認します。  
  
 受信場所の作成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [分離 WCF 受信アダプターでの WCF サービスの公開](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: WCF-BasicHttp アダプターを使用した WCF サービスの公開](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)