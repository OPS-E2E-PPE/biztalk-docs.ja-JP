---
title: Wcf-siebel アダプターを使用してポートの構成 |Microsoft Docs
description: BizTalk server、Siebel eBusiness Applications アダプターを使用する WCF Siebel 送信ポートを作成します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6314104-c742-440c-b530-b5a82295353a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eec0ca12c8b77d9327ddc7fae6136c75ff99202
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975523"
---
# <a name="configure-a-port-using-the-wcf-siebel-adapter"></a>Wcf-siebel アダプターを使用してポートを構成します。
Siebel システムを使用して送信操作を実行する WCF Siebel 送信ポートを構成する方法、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。
  
## <a name="deploy-adapters-for-sending-messages-to-a-siebel-system"></a>Siebel システムにメッセージを送信するためのアダプターを展開します。  
 使用して Siebel システムにメッセージを送信するための WCF Siebel 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. Wcf-siebel アダプターの追加、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。 手順については、[Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)を参照してください。  
  
3. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
4. 展開するアプリケーションを展開し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
5. 右クリックし**送信ポート**、 をポイント**新規**、BizTalk Server と Siebel システム間の通信のモードによって構成するポートの種類 をポイントします。  
  
6. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
7. **型**ドロップダウン リスト、選択、Wcf-siebel アダプター前に追加しをクリックする**構成**します。  
  
8. トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  
  
   1. をクリックして、**全般**タブをクリックし、**構成**ボタンをクリックし、接続パラメーターの値を指定します。 接続 URI の詳細については、[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)を参照してください。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)の各操作のアクションの一覧。 たとえば、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すアクションは。  
  
      ```  
      http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
      ```  
  
   3. をクリックして、**バインド**タブし、バインドのプロパティの値を指定します。 詳細については、[Siebel のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)を参照してください。  
  
   4. をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  
  
      - 選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
      - 選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
        BizTalk Server に関するセキュリティの詳細については、[Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)を参照してください。  
  
   5. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
9. **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
10. 手順 5. で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
11. 手順 5. で静的な送信請求-応答ポートを選択した場合は、指定の送信および受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
12. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)