---
title: Biztalk WCF カスタム アダプターと Siebel アダプターを使用するポートの構成 |Microsoft Docs
description: 作成 wcf-custom 送信ポートと受信ポートを BizTalk server、Siebel eBusiness Applications アダプターを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df6d9e9cea34a9bfd95765ad4d37f51fcf55f4ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017991"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a>Wcf-custom アダプターと Siebel アダプターを使用してポートを構成します。
このトピックでは、Wcf-custom を構成する方法については送信ポートを使用して Siebel システムでの送信操作を実行する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a>Siebel システムへのメッセージ送信用のアダプターの展開  
 使用して Siebel システムにメッセージを送信するための Wcf-custom 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
 
1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
2. コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。  
  
3. 展開するアプリケーションを展開し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。  
  
4. 右クリックし**送信ポート**、 をポイント**新規**、BizTalk Server と Siebel システム間の通信のモードによって構成するポートの種類 をポイントします。  
  
5. **送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。  
  
6. **型**ドロップダウン リストで、 **Wcf-custom**クリック**構成**します。  
  
7. **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1. をクリックして、**全般** タブで、**アドレス (URI)** フィールドは、Siebel システムに接続する接続 URI を指定します。 接続 URI の詳細については、次を参照してください。 [Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。  
  
   2. **全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。 参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)の各操作のアクションの一覧。 たとえば、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すアクションは。  
  
      ```  
      http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
      ```  
  
   3. をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **siebelBinding**します。 によって公開されるさまざまなバインドのプロパティを指定することも、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 詳細については、次を参照してください。 [Siebel のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  
  
   4. をクリックして、**資格情報**タブし、次のいずれかの操作を行います。  
  
      - 選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。  
  
      - 選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。  
  
        BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)します。  
  
   5. 戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。  
  
8. **送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。  
  
9. 手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。 **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
10. 手順 4. で静的な送信請求-応答ポートを選択した場合は、送信を指定し、受信パイプライン。  
  
    1.  **送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。  
  
    2.  **受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。  
  
11. **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
[Siebel アダプターを物理ポートのバインドを手動で構成します。](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)