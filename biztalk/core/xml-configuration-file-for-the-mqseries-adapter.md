---
title: MQSeries アダプターの XML 構成ファイル |Microsoft Docs
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
ms.openlocfilehash: 32ba4c90f082b15c43fd04f8c2de22b31f16bdfd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295364"
---
# <a name="xml-configuration-file-for-the-mqseries-adapter"></a>MQSeries アダプターの XML 構成ファイル
XML 構成ファイルを読み取り**mqsconfigwiz** Windows バージョンのウィザードを使用して、ユーザーが入力と同じ情報が含まれています。 この情報には、アプリケーション id とユーザー ID とパスワードが必要な場合、ロール名、およびそのロールの一部であるユーザーの一覧が含まれています。  
  
 ファイルの例を次に示します。  
  
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
  
 使用することができます**thisuser**、 **InteractiveUser**、 **LocalService**、または**NetworkService**値として**AppIdentity**. 使用して、 **userid**と**パスワード**要素でのみ**thisuser**します。  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのサイレント構成](../core/silent-configuration-of-the-mqseries-adapter.md)