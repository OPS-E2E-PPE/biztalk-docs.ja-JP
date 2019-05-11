---
title: 送信ポート グループのフィルターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send port groups
- send port groups, filters
- send port groups, configuring
- configuring, send port groups
- managing [send port groups], filters
- managing [send port groups], configuring
ms.assetid: 4c4bb408-5146-4740-a1d4-0ee72ec123fb
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4c5d54608da91f76337cba13390baf5ded2b27d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341478"
---
# <a name="how-to-configure-filters-for-a-send-port-group"></a>送信ポート グループのフィルターを構成する方法
このトピックでは、使用する方法を説明します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールに送信ポート グループの 1 つまたは複数のフィルターを構成します。 単純なメッセージングを作成するためのフィルターまたはコンテンツ ベースのルーティング (CBR) アプリケーションを使用することができます。 フィルターは、メッセージのプロパティやフィールド、送信ポート グループにルーティングするメッセージを決定するための条件を設定します。 フィルターは、オーケストレーションが送信ポート グループにルーティングするメッセージをフィルター処理されません。  
  
 メッセージ プロパティ、演算子、および演算子を使用して、プロパティに対して検証される値から成る 1 つまたは複数のフィルター式を作成することができます。  
  
 たとえば、次のような式を作成できます。  
  
 MSMQ.MsgID = 1  
  
 このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。  
  
 さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。  
  
 MSMQ.MsgID = 1 OR  
  
 SMTP です。MyServer を =  
  
 この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。  
  
> [!NOTE]
>  フィルターは正しく機能をスキーマが存在しない場合は、警告が表示されましていない別のアプリケーションでプロパティ スキーマを使用する 1 つのアプリケーションで、送信ポート グループのフィルターを作成し、新しい BizTalk グループに最初のアプリケーションをインポートすると、ときに、アプリケーションをインストールして開始します。 この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。  
  
> [!NOTE]
>  アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中に、送信ポート グループ用のフィルターを構成できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-filters-for-a-send-port-group"></a>送信ポート グループのフィルターを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと、送信ポート グループ フィルターを構成する BizTalk アプリケーションを展開します。  
  
3. クリックして**送信ポート グループ**は、送信ポート グループを右クリックし、**プロパティ**、順にクリックします**フィルター**します。  
  
4. 次の表に示すようにフィルターを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**削除**|クリックすると、選択したフィルター式を削除します。|  
   |**[上へ移動]**|選択したプロパティのフィルター式のシーケンス内で移行する をクリックします。|  
   |**[下へ移動]**|クリックすると、選択したプロパティをフィルター式のシーケンス内で下へ移動します。|  
   |**プロパティ**|一覧で、このフィルター式で使用するメッセージ プロパティをクリックします。|  
   |**[演算子]**|入力するか、式の演算子を選択します。|  
   |**[値]**|プロパティの検証に使用する値を入力します。 指定できる値の型は、プロパティの型によって異なります。 プロパティの値の種類が受け入れられるを表示するには、プロパティにマウスを移動します。 使用可能な値は次のとおりです。Int。(整数)これは、整数でなければなりません。 文字列:文字列を返します。 dateTime:日付や時間。NET でサポートされている形式です。 詳細についてはします。NET でサポートされる時刻の形式は、.NET Framework ヘルプの「DateTimeFormatInfo クラス」を参照してください。|  
   |**グループ化**|選択**と**または**または**フィルター式の間のリレーションシップを示します。|  
  
## <a name="see-also"></a>参照  
 [送信ポート グループの作成および構成](../core/creating-and-configuring-send-port-groups.md)