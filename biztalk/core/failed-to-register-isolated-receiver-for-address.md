---
title: アドレスの分離受信場所の登録に失敗しました |Microsoft Docs
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
ms.openlocfilehash: 7db73ecd84218f19dbc576ae3e94dec6cef4218d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388134"
---
# <a name="failed-to-register-isolated-receiver-for-address"></a>アドレスの分離受信場所を登録できませんでした
## <a name="details"></a>詳細  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  製品名   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| 製品バージョン |                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                        |
|    イベント ID     |                                                    0                                                    |
|  イベント ソース   |                                                    0                                                    |
|    コンポーネント    |                                                    0                                                    |
|  シンボル名  |                                                    0                                                    |
|  メッセージ テキスト   | アドレスの分離受信場所を登録できませんでした"{0}"; 受信場所が存在しないか無効にします。 |
  
## <a name="explanation"></a>説明  
 このエラーは、公開された WCF 分離受信場所であることを示します見つかりませんでした。 対応する受信場所。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで、BizTalk WCF サービス公開ウィザード生成が存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。  
  
 作成の詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [分離 WCF 受信アダプターでの WCF サービスの公開](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: Wcf-basichttp アダプターで WCF サービスの公開](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)