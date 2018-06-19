---
title: 受信場所 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, properties
- receive locations, about receive locations
- receive locations
- receive locations, receive location types
ms.assetid: be5f7e5d-b63f-42f6-985e-895ba3912d34
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9866edd5dfa6f953c4e847f191891bd7e6bc25ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268626"
---
# <a name="receive-locations"></a>受信場所
受信場所の作成時には、着信メッセージを受信するアドレスと、そのアドレスで受信したメッセージを処理するメッセージング パイプラインを指定します。 受信場所の作成および有効化は、管理者のみが行えます。  
  
 管理者は BizTalk 管理コンソールを使用して、受信場所を作成し、オーケストレーションにバインドし、有効または無効にし、受信場所のグローバル プロパティを設定します。  
  
 管理者 (BizTalk 管理コンソールを使用) は、以下の手順に従って受信場所を作成します。  
  
1.  受信場所を作成します。  
  
2.  受信場所をホストに関連付けます。  
  
3.  受信場所をオーケストレーションにバインドします。  
  
4.  受信場所を有効にします。  
  
5.  受信場所は、メッセージを受信します。  
  
> [!NOTE]
>  Windows Management Instrumentation (WMI) で受信場所に対して行った変更は、BizTalk 管理コンソールの受信場所の表示に影響します。 たとえば、管理者が WMI を使用して新しい受信場所を作成した場合、その受信場所は BizTalk 管理コンソールに表示されます。 同様に、管理者が受信場所を削除した場合、その受信場所は BizTalk 管理コンソールに表示されなくなります。  
  
> [!IMPORTANT]
>  各受信場所には一意の名前が必要です。 2 つの受信場所と同じで、同じ名前を持つことはできません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。  
  
> [!IMPORTANT]
>  受信場所の格納先には強力なアクセス制御リスト (ACL) を設定することをお勧めします。 たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。  
  
## <a name="receive-location-types"></a>受信場所の種類  
 受信場所には次の 2 種類があります。  
  
-   一方向。 メッセージを格納し、同期応答を待機しないアプリケーションに使用します。  
  
-   要求 - 応答。 メッセージへの応答を求めるアプリケーションに使用します。  
  
## <a name="receive-location-properties"></a>受信場所のプロパティ  
 受信場所にグローバルとアダプター固有のプロパティがあります。 BizTalk 管理コンソールを使用して、管理者は、特定のアダプターに関連付けられている受信場所のすべてのグローバル プロパティを設定します。  
  
 受信場所のプロパティへの変更は、順番に行われます。 ソリューション開発者がプロパティ値を変更する場合、特定の受信場所、新しいプロパティ値のオーバーライドのグローバル プロパティの値を受信場所を BizTalk 管理コンソールで管理者が設定します。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)   
 [成果物](../core/artifacts.md)