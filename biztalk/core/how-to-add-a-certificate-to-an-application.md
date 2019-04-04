---
title: アプリケーションに証明書を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, certificates
- managing [certificates], adding to applications
- certificates, applications
- managing [applications], certificates
- managing [certificates], applications
- managing [resources], certificates
ms.assetid: 7c615002-6627-4134-9c2b-bf1c89d626c2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 764853a43f29910727b302d6554cb3bbd741abd8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986419"
---
# <a name="how-to-add-a-certificate-to-an-application"></a>証明書をアプリケーションに追加する方法
ここでは、コマンド ラインを使用して、BizTalk アプリケーションに証明書を追加する方法について説明します。 このオプションは、BizTalk Server 管理コンソールでは利用できません。 BizTalk アプリケーションに証明書を追加することで、証明書をアプリケーションと一緒にパッケージ化して、BizTalk グループの 1 つから別のグループに送信することができるようになります。 証明書を使用すると、ID を検証して送信ポートと受信場所へのセキュリティで保護されたリンクを確立することができます。 詳細については、[送信ポートに証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-send-port.md)と[受信場所に証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-receive-location.md)を参照してください。  
  
 証明書をアプリケーションに追加する際には、次の重要事項を念頭に置いてください。  
  
-   証明書をアプリケーションに追加すると、その証明書は BizTalk 管理データベースに証明書アイテムとして追加されます。 そのアプリケーションをインストールすると、証明書がローカル コンピューターの "その他のユーザー" 証明書ストアにインポートされるので、証明書をこのストアへインポートする追加手順を事前に実行しなくても送信ポートまたは受信場所に証明書を割り当てることができます。 BTSTask を使用して証明書を追加する場合は、その証明書が "その他のユーザー" 証明書ストアにあらかじめ存在している必要があり、拇印を指定する必要があります。  
  
    > [!NOTE]
    >  証明書をエクスポートすると、秘密キーが削除されます。 アプリケーションをインストールすると証明書は証明書ストアにインポートされますが、暗号化されたメッセージの解読にその証明書を使用することはできません。ただし、暗号化されたメッセージの送信には使用できます。 証明書を前者の目的に使用する必要がある場合、証明書が使用される送信ポートをホストしているコンピューターの "その他のユーザー" 証明書ストアに証明書を再インストールする必要があります。  
  
-   ベスト プラクティスとして、複数アプリケーションの送信ポートまたは受信場所で同じ証明書を使用する場合は、独立したアプリケーションで証明書を展開した後、この証明書を使用する各アプリケーションから先ほどのアプリケーションを参照することをお勧めします。 これは、BizTalk グループ内で複数の証明書に同じ捺印を使用できないためです。したがって、2 つの異なるアプリケーションの同じ証明書をインポートすることはできません。 同じ証明書を使用する 2 つのアプリケーションをインポートしようとすると、最初のインポートは成功しますが、2 番目のインポートは成功しません。 [上書き] インポート オプションを使って既存の証明書を上書きしようとしても、その証明書は別のアプリケーションに含まれているため上書きできません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-add-a-certificate-to-an-application"></a>証明書をアプリケーションに追加するには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。  
  
2. 次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。  
  
    **BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:Certificate** **[/overwrite]****「/Thumbprint」:"**<em>値</em>**"** [**/Server:**<em>値</em>] [**/データベース:**<em>値</em>]  
  
    例:  
  
    **BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:Certificate/Overwrite「/thumbprint」:"04 a2 8e 32 24 f9 36 b9 42 81 12 71 3a d2 ef db c7 9c 83 dc"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**  
  
   |パラメーター|値|  
   |---------------|-----------|  
   |**/ApplicationName**|証明書を追加する BizTalk アプリケーションの名前。 アプリケーション名が指定されなかった場合、グループの既定の BizTalk アプリケーションが使用されます。 名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。|  
   |**/型**|**System.BizTalk:Certificate** (この値小文字は区別されません)。|  
   |**/上書き**|既存の証明書を更新するためのオプション。 指定しなかった場合、追加する証明書と同じ拇印 (Thumbprint) プロパティを持つ証明書が既にアプリケーションに存在した場合、追加操作は失敗します。 Thumbprint プロパティは、証明書スナップインで証明書をダブルクリックし、[詳細] タブをクリックして表示できます。詳細については、証明書スナップインのドキュメントで「証明書情報の表示」を参照してください。|  
   |**/拇印**|証明書の拇印プロパティ (、*拇印*はデータのダイジェストです)。 この値は、二重引用符 (") で囲む必要があります。|  
   |**/サーバー**|BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。<br /><br /> インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。 ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。<br /><br /> 例 :<br /><br /> Server=MyServer<br /><br /> Server=MyServer\MySQLServer,1533<br /><br /> 指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。|  
   |**/データベース**|BizTalk 管理データベースの名前。 指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。|  
  
## <a name="see-also"></a>参照  
 [.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md)   
 [AddResource コマンド: 証明書](../core/addresource-command-certificate.md)   
 [BizTalk アプリケーションの作成と変更](../core/creating-and-modifying-biztalk-applications.md)