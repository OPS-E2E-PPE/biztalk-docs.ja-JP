---
title: AS2 セキュリティに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b291e000-630d-49a1-8e19-f76c4dfee294
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e57a9ecd84f3087dc860a13c9e9f06d7e0859947
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380797"
---
# <a name="known-issues-with-as2-security"></a>AS2 セキュリティに関する既知の問題
このトピックでは、のセキュリティに関する既知の問題を説明します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 ソリューション。  
  
## <a name="the-as2-decoder-will-not-validate-that-a-certificate-is-configured-on-the-host-or-for-the-destination-party"></a>AS2 デコーダーは、ホストまたは送信先パーティの証明書が構成されていることを検証できません。  
 証明書ストアにそのメッセージのプライベート証明書が構成されている限り、AS2 デコーダーはメッセージの解読します。 ただし、AS2 デコーダーでは、暗号化解除証明書がホストに構成されている証明書と同じであるが無効です。 1 つ以上の証明書では、受信したメッセージを暗号化できます。  
  
## <a name="storing-as2-messages-in-wire-format-can-lead-to-a-security-issue"></a>セキュリティ上の問題につながる AS2 メッセージをワイヤ形式で格納します。  
 証明書を使用しない場合、AS2 メッセージをワイヤ形式で、受信の否認不可 (NRR) データベースに格納するはお勧めできません。 これによりセキュリティ上の問題になる可能性。  
  
## <a name="messages-or-mdns-to-be-stored-in-the-nrr-database-should-be-signed"></a>NRR データベースに格納するには、メッセージまたは Mdn に署名を付ける  
 受信の否認を保証するためには、認証と、該当するメッセージの整合性を確立する必要があります。 実行のお勧めの方法は、メッセージのデジタル署名を使用してためです。 その結果、メッセージまたは Mdn を否認不可データベースに格納する AS2 パーティ プロパティを構成する場合は、メッセージまたは格納する Mdn に署名する AS2 プロパティを構成する必要があります。  
  
## <a name="biztalk-server-will-be-unable-to-decrypt-a-message-saved-in-wire-format-if-the-certificate-is-not-valid"></a>BizTalk Server を証明書が有効でない場合は、ワイヤ形式で保存されたメッセージを復号化することはできません。  
 **現象**  
  
 BizTalk Server がワイヤ形式で否認不可データベースに保存された受信 AS2 メッセージを復号化できません。  
  
 **考えられる原因**  
  
 メッセージを復号化するために必要な証明書が期限切れか、失効しています。 これは、AS2 メッセージが否認不可データベースに保存されてから一定の時間が経過している場合に発生する可能性が高くなります。 このような場合として、メッセージの有効な証明書にすぐにアクセスしていない必要があります。  
  
 **解決方法**  
  
 メッセージの復号化の有効な証明書を取得します。  
  
## <a name="the-inner-envelope-of-a-signed-as2-message-must-not-be-changed-after-the-signature-has-been-calculated"></a>署名が計算された後、署名付きの AS2 メッセージの内部エンベロープを変更しないでください。  
 AS2 メッセージが署名されたときに、署名は、内部エンベロープのヘッダーとペイロードにに基づいて計算されます。 署名が計算された後は、内部エンベロープを変更する場合、署名が破損します。 境界ヘッダー、または境界ヘッダー以外は変更できますが、境界ヘッダー内のすべてを変更しないでください。  
  
## <a name="use-the-same-logon-for-the-in-process-host-instance-and-the-isolated-host-instance-to-ensure-that-personal-store-is-recognized"></a>インプロセス ホスト インスタンスと分離ホスト インスタンスの同じログオンを使用して、その個人ストアが認識されることを確認するには  
 個人証明書ストアは、メッセージ ログオン資格情報を持つが、ホスト インスタンスに関連付けられたユーザーのユーザー プロファイルが読み込まれている場合にのみを処理できるようにします。 署名と暗号化解除証明書 (ユーザーの秘密キー) の個人用ストアが使用されます。 既定では、インプロセス ホスト インスタンスのユーザー プロファイルが読み込まれるただし、ユーザー プロファイルは、分離ホスト インスタンスの既定では読み込まれません。 分離ホストのユーザー プロファイル、アプリケーションで読み込むことができます。 または、インプロセス ホスト インスタンスと分離ホスト インスタンスを同じログオンを使用してこの問題を回避することができます。  
  
 アプリケーションの負荷、ユーザー プロファイルするのではなく、プロファイルの読み込みに空のサービスを作成できます。 空のサービスを作成する方法の詳細については、次を参照してください。[方法。Windows サービスの作成](http://go.microsoft.com/fwlink/?LinkId=196492)です。 コンピューターの管理 ダイアログ ボックスを開く、サービスを作成した後、サービスのプロパティ ダイアログ ボックスを開く、 をクリックして、**ログオン** タブで **アカウント**を使用するログオン名を入力してください、分離ホスト インスタンス、およびクリック**OK**します。 そのログオン ユーザーのユーザー プロファイルの読み込みにサービスを手動で開始できます。  
  
## <a name="the-key-usage-attribute-of-a-certificate-must-match-the-certificates-use"></a>証明書のキー使用法 属性は、証明書の使用と一致する必要があります。  
 AS2 トランスポートに使用される証明書には、その使用目的に必要な属性が必要です。 署名および署名の検証を行う証明書のキー使用法 属性は、デジタル署名をする必要があります。 暗号化と復号化は、証明書のキー使用法 属性はデータの暗号化またはキーの暗号化である必要があります。 キー使用法属性は、証明書をダブルクリックし、証明書 ダイアログ ボックスで、詳細 タブをクリックすると、キー使用法フィールドをチェックして確認できます。  
  
## <a name="the-certificate-resolution-list-will-be-verified-for-an-outgoing-mdn-if-the-as2-to-property-is-not-set-for-the-party"></a>場合、送信 MDN に対して証明書解決の一覧を確認するは、AS2 のプロパティに設定されていないパーティの  
 送信 MDN の既定のアグリーメントでは、証明書解決の一覧の検証が実行されます。 この検証を実行しないようにする場合、ことを確認します。 適切な AS2、パーティ プロパティを設定すると、受信側パーティを解決できると、パーティのプロパティを特定できるようにします。 そうである場合、証明書の解像度リストの検証を要求する既定のアグリーメントは使用されません。 また、AS2 パーティ プロパティの [全般] ページで、証明書失効リストのチェック プロパティを無効にする必要があります。