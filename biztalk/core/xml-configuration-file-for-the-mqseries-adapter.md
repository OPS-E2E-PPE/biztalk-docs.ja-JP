---
title: MQSeries アダプターの構成ファイルを XML |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, mqsconfigwiz
- configuring [MQSeries adapters], silent configuration
- MQSeries adapters, silent configuration
- configuring [MQSeries adapters], mqsconfigwiz
- mqsconfigwiz [MQSeries adapters]
ms.assetid: 5f19e55c-0f2c-46d7-bb5d-1eb147c296b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a0356c69b90f0dcfd5fc636b302a97b2de5674b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289770"
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a>MQSeries アダプターの XML 構成ファイル
XML 構成ファイルを読む**mqsconfigwiz** Windows 版のウィザードを使用する場合、ユーザーが入力したのと同じ情報が含まれています。 たとえば、アプリケーション ID、ユーザー ID とパスワード (必要な場合)、ロール名、およびそのロールに属しているユーザーの一覧などがあります。  
  
 このファイルの例を次に示します。  
  
```  
<MQSeriesConfig>  
    <AppIdentity>thisuser</AppIdentity>  
    <userid>domain\username</userid>  
    <password>Bippity.Boppity</password>  
    <rolename>CreatorOwner</rolename>  
    <userlist>  
        <username>domain\user1</username>  
        <username>domain\user2</username>  
    </userlist>  
</MQSeriesConfig>  
```  
  
 使用することができます**thisuser**、 **InteractiveUser**、 **LocalService**、または**NetworkService**の値として**AppIdentity**. 使用して、 **userid**と**パスワード**のみを持つ要素**thisuser**です。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプタのサイレント構成](../core/silent-configuration-of-the-mqseries-adapter.md)