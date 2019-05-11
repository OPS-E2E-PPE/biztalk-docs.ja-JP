---
title: 見つかりませんメタデータの受信場所 |。Microsoft Docs
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
ms.openlocfilehash: 8910b5877e05d72e52707c93b0fb0bf99ae78cd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398241"
---
# <a name="receive-location-for-metadata-not-found"></a>メタデータの受信場所が見つかりません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                           |
| 製品バージョン |                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                       |
|    イベント ID     |                                                                   0                                                                   |
|  イベント ソース   |                                                                   0                                                                   |
|    コンポーネント    |                                                                   0                                                                   |
|  シンボル名  |                                                                   0                                                                   |
|  メッセージ テキスト   | 受信場所"{0}"のメタデータが見つかりません。 (Web.config の受信場所マッピングを確認および受信場所が存在することを確認します。) |
  
## <a name="explanation"></a>説明  
 このエラーは、公開された WCF 分離受信場所であることを示します見つかりませんでした。 対応するメタデータの受信場所。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。BizTalk 管理コンソールで生成される BizTalk WCF 公開ウィザードが存在し、開始は、Web.config ファイルの receiveLocationName 属性で、受信場所が指定されているいることを確認します。  
  
 詳細については、受信場所、次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [WCF サービスの公開](../core/publishing-wcf-services.md)  
  
-   [Wcf-basichttp 受信場所を構成する方法](http://msdn.microsoft.com/library/43f18e5d-ba28-453c-b8ce-5bcdc6f27fdd)  
  
-   [Wcf-wshttp 受信場所を構成する方法](../core/how-to-configure-a-wcf-wshttp-receive-location.md)  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [チュートリアル: Wcf-netmsmq アダプターで WCF サービスの公開](../core/walkthrough-publishing-wcf-services-with-the-wcf-netmsmq-adapter.md)