---
title: 送信ポート グループを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send port groups
- send port groups, creating
- managing [send port groups], creating
ms.assetid: de3e72aa-83f4-4760-9f39-a488f904f1d3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e58d6405c9bc979f473d90be4bd4659111373a20
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339898"
---
# <a name="how-to-create-a-send-port-group"></a>送信ポート グループを作成する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アプリケーションで送信ポート グループを作成して、送信ポートを追加する方法について説明します。 送信ポート グループには、静的な一方向の送信ポートのみ追加できます。 メッセージをルーティングするには、送信ポート グループに少なくとも 1 つの送信ポートが存在する必要があります。  
  
 別のアプリケーションに存在する送信ポートを追加することはできません。 別のアプリケーションの送信ポートを追加する場合は、送信ポート グループのあるアプリケーションから目的の送信ポートがあるアプリケーションへの参照を追加する必要があります。 手順については、次を参照してください。[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-create-a-send-port-group"></a>送信ポート グループを作成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、送信ポート グループを作成する BizTalk アプリケーションを展開します。  
  
3. 右クリック**送信ポート グループ**、 をポイント**新規**、 をクリックし、**送信ポート グループ**します。  
  
4. **名前**ボックスに、送信ポート グループの名前を入力します。  
  
5. **送信ポート**、下のドロップダウン リストをクリックして**名前**、送信ポート グループに追加する送信ポートをクリックします。 グループに追加する送信ポートごとにこの手順を繰り返します。 新しい送信ポートを作成し、追加してをクリックします **\<新しいポートを送信しています...\>** し、指示に従って、[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。  
  
6. 送信ポートの送信ポート グループに追加したら、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [送信ポート グループの作成および構成](../core/creating-and-configuring-send-port-groups.md)