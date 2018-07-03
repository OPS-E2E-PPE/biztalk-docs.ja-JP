---
title: 送信ポートのフィルターを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, configuring
- filters, send ports
- configuring, filters
- managing [send ports], configuring
- send ports, configuring
- send ports, filters
- managing [send ports], filters
ms.assetid: ad13ca8e-bb1d-4449-8163-49dd9d5d92f8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae9c522f982ca82bf865bcfe6c4b481b0133ec7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988179"
---
# <a name="how-to-configure-filters-for-a-send-port"></a>送信ポートのフィルターを構成する方法
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、送信ポートのフィルターを構成する方法について説明します。 フィルターを使用することにより、シンプルなメッセージング アプリケーションや、コンテンツ ベースのルーティング (CBR) アプリケーションを作成できます。 フィルターとは、どのメッセージをどの送信ポートにルーティングするかを定義した、メッセージのプロパティやフィールドに対する条件設定です。 オーケストレーションによって送信ポートにルーティングされるメッセージについては、フィルターでは制御できません。  
  
 フィルター式は、メッセージのプロパティ、演算子、および (演算子を介してプロパティと比較される) 値で構成されます。複数のフィルター式を作成することもできます。  
  
 たとえば、次のような式を作成できます。  
  
 MSMQ.MsgID = 1  
  
 このフィルターを適用した場合、送信ポート グループは、MSMQ のメッセージ ID が 1 であるメッセージだけをサブスクライブします。  
  
 さらに式を追加したり、AND や OR で他の式と組み合わせることもできます。その例を次に示します。  
  
 MSMQ.MsgID = 1 OR  
  
 SMTP.From = MyServer  
  
 この場合、送信ポート グループは、MSMQ メッセージ ID が 1 であるか、または、送信元が MyServer という名前の SMTP サーバーであるすべてのメッセージをサブスクライブします。  
  
> [!NOTE]
>  別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポートにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストールおよび起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。 この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中に送信ポート用のフィルターを構成するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに属するアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-configure-filters-for-a-send-port"></a>送信ポートのフィルターを構成するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、送信ポート フィルターを構成する BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**フィルター**します。  
  
4. 次の表に示すようにフィルターを構成し、 **OK**します。  
  
   |プロパティ|目的|  
   |--------------|----------------|  
   |**削除**|選択したフィルター式を削除する場合にクリックします。|  
   |**[上へ移動]**|選択したプロパティを、フィルター式のシーケンス内で前方に移動する場合にクリックします。|  
   |**[下へ移動]**|選択したプロパティを、フィルター式のシーケンス内で後方に移動する場合にクリックします。|  
   |**プロパティ**|フィルター式に使用するメッセージ プロパティを一覧から選んでクリックします。|  
   |**[演算子]**|式の演算子を入力または選択します。|  
   |**[値]**|プロパティに対して検証する値を入力します。 使用できる値の型は、プロパティの種類により異なります。 プロパティにマウス カーソルを合わせると、そのプロパティ値に使用できる型を確認できます。 使用可能な値は次のとおり: Int: (整数) この整数である必要があります。 文字列: 文字列を返します。 dateTime: 日付や時間。NET でサポートされている形式です。 .NET でサポートされる時刻形式の詳細については、.NET Framework ヘルプの「DateTimeFormatInfo クラス」を参照してください。|  
   |**グループ化**|選択**と**または**または**これと他のフィルター式の間のリレーションシップを示します。|  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)