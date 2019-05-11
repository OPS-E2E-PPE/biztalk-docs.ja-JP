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
ms.openlocfilehash: 17aa261f12d7783a15b998c5eed9743ee7af07dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398222"
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
|  メッセージ テキスト   | アドレスの受信場所"{0}"が見つかりませんでした。 (BizTalk 受信場所が無効になっています)。 |
  
## <a name="explanation"></a>説明  
 このエラーは、公開された WCF 分離受信場所であることを示します見つかりませんでした。 対応する受信場所。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。  
  
 作成の詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [分離 WCF 受信アダプターでの WCF サービスの公開](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: Wcf-basichttp アダプターで WCF サービスの公開](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)