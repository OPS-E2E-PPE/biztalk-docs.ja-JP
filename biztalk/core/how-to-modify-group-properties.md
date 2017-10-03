---
title: "グループのプロパティを変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, groups
- configuring, groups
- groups, configuring
- managing [groups], properties
- groups, modifying
- managing [groups], modifying
- groups, properties
ms.assetid: 59e0853d-81b0-43f9-85bf-099868e25fad
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a191011b6824086e26c72ce5e5a182a167ca0e37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-group-properties"></a>グループのプロパティを変更する方法
ここで示す手順を使用すると、BizTalk Server グループのグローバル プロパティを構成して、署名証明書の選択、キャッシュ更新間隔の変更、および BizTalk Server でサイズの大きいメッセージをどのように処理するかという指定を行えます。 BizTalk Server グループのプロパティの詳細については、次を参照してください。 [BizTalk グループ](../core/biztalk-groups.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-configure-biztalk-group-properties"></a>BizTalk グループのプロパティを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]を BizTalk グループを展開しを右クリックして**BizTalk グループ**、順にクリック**プロパティ**です。  
  
3.  **グループのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|グループ名を入力します。 グループ名の長さは 128 文字以下にしてください。 このボックスに名前が横に表示されます、**グループ**コンソール ツリーで、サーバー名および BizTalk 管理データベース名と共にノード。|  
    |**[サーバー]**|BizTalk 管理データベースが物理的に格納されているサーバーを表示します。|  
    |**データベース**|このグループのすべての構成設定が格納されている BizTalk 管理データベースを表示します。|  
    |**SSO サーバー名**|このコンピューターでアダプター固有の情報の格納、または情報へのアクセスに使用する、エンタープライズ シングル サインオン (SSO) サーバーの名前を入力します。 これは、SSO データベースへの接続に使用する SSO サーバーの名前です。|  
    |**BizTalk 管理者グループ**|インストール後に BizTalk Server 環境を管理する権限が与えられている管理者グループ名を表示します。|  
    |**BizTalk Operators グループ**|構成の表示、クエリの実行、コンピューターの保守と基本的なアプリケーションの監視を行う権限を持つ Operators グループの名前を表示します。|  
    |**BizTalk Server B2B Operators**|B2B Operators グループの名前が表示されます。|  
  
4.  **データベース** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**データベース**|アプリケーションのすべてのデータベースの名前と、データベースが存在するサーバーの名前を、構成時の指定どおりに表示します。|  
  
5.  **証明書** タブで、次の操作をクリックして**OK**:  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**共通名**|選択した証明書の説明を表示します。|  
    |**拇印**|このグループから送信されるメッセージのデジタル署名に使用される秘密キー証明書の拇印を表示します。 証明書の拇印には、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進数字 (0 ~ 9 の数字) または a ~ F の文字の形式があります。|  
    |**証明書を削除します。**|表示されている証明書を削除する場合にクリックします。|  
    |**参照**|クリックすると表示、**証明書の選択**ダイアログ ボックスで、署名証明書の現在のユーザーまたは個人用ストアに、グループに使用するを選択します。|  
  
## <a name="see-also"></a>参照  
 [グループを管理します。](../core/managing-groups.md)   
 [BizTalk グループ](../core/biztalk-groups.md)   
 [サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md)   
 [1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md)   
 [グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md)