---
title: 受信場所 |Microsoft Docs
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
ms.openlocfilehash: 0fefe11eb38575a7225b6cc88c3977df6bab685b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398212"
---
# <a name="receive-locations"></a>受信場所
受信場所を作成するには、受信メッセージを受信し、そのアドレスで受信したメッセージを処理するメッセージング パイプラインするアドレスを指定する必要があります。 管理者のみ作成でき、受信場所を有効にします。  
  
 受信場所を作成する BizTalk 管理コンソールを使用して、管理者、受信オーケストレーションに場所のバインド、受信場所の有効化、無効にする受信場所、および受信場所のグローバル プロパティのセット。  
  
 管理者 (BizTalk 管理コンソールを使用) では、受信場所を作成する次の手順に従います。  
  
1.  受信場所を作成します。  
  
2.  受信場所をホストに関連付けます。  
  
3.  受信場所をオーケストレーションにバインドします。  
  
4.  受信場所を有効にします。  
  
5.  受信場所は、メッセージを受信します。  
  
> [!NOTE]
>  受信 Windows Management Instrumentation (WMI) に影響をどのように使用して行われた場所に変更の受信場所、BizTalk 管理コンソールに表示されます。 たとえば、管理者は WMI を新しく作成する受信場所を受信する場合、BizTalk 管理コンソールで場所が表示されます。 同様に、管理者は、受信場所を削除した場合、受信場所を BizTalk 管理コンソールから表示されなくなります。  
> 
> [!IMPORTANT]
>  各受信場所には一意の名前が必要です。 2 つの受信場所と同じで、同じ名前を持つことはできません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]展開します。  
> 
> [!IMPORTANT]
>  設定されている強力なアクセス制御リスト (ACL)、受信場所の格納場所をお勧めします。 たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。  
  
## <a name="receive-location-types"></a>受信場所の種類  
 2 つの種類のある受信場所  
  
-   一方向です。 アプリケーション メッセージを渡すし、同期応答を待たずに使用します。  
  
-   要求-応答します。 メッセージに対する応答を必要とするアプリケーションで使用します。  
  
## <a name="receive-location-properties"></a>受信場所のプロパティ  
 受信場所にグローバルとアダプター固有のプロパティがあります。 BizTalk 管理コンソールを使用して、管理者は、特定のアダプターに関連付けられている受信場所のすべてのグローバル プロパティを設定します。  
  
 受信場所のプロパティに対する変更が順番に実行します。 ソリューション開発者がプロパティ値を変更した場合、特定の受信場所、新しいプロパティ値のオーバーライドをグローバル プロパティの値の受信場所、管理者は、BizTalk 管理コンソールで設定します。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)   
 [アイテム](../core/artifacts.md)