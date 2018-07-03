---
title: Server ランタイムのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, server runtime
- servers, security
- servers, runtime
ms.assetid: 40f5ca3e-d9d3-4543-bd38-82283c343b76
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c690c6e34e5ac8d5f70bc58cfd36e4e99006e8b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976267"
---
# <a name="server-runtime-security"></a>Server ランタイムのセキュリティ
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission、安全かつ確定的な方法でビジネス ユーザー、バックエンド システム、および行う SWIFT ネットワーク エンドポイント間で SWIFT メッセージのフローを制御します。 ビジネス ユーザーによって送信されたメッセージを認証し、メッセージのデータおよびビジネス ルールの正確性を検証します。、または SWIFT ネットワークへの最終的な配信のバックエンド システムにメッセージをルーティングします。 デジタル証明書の詳細については、MSDN ライブラリの Web サイトでの暗号化と署名証明書 を参照してください。 [ http://go.microsoft.com/fwlink/?linkid=50285](http://go.microsoft.com/fwlink/?linkid=50285)します。  
  
 Message Repair and New Submission は、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーション アプリケーションでホストされ、実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ コンテキスト。 としてセキュリティで保護された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アプリケーションを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]前に説明したセキュリティ機能。 Message Repair and New Submission も定義し、SWIFT メッセージの作成、修復、承認、および送信する特定のユーザー レベルのセキュリティ ポリシーを次のように強制します。  
  
- 新しいまたは修復のすべてのメッセージが送信された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]Message Repair and New Submission の使用が信頼されたユーザーから送信する必要があります。  
  
- 作成またはメッセージを修復する信頼されたユーザーは、適切な承認と権限が必要です。 承認またはメッセージを拒否する信頼されたユーザーは、適切な承認と権限が必要です。  
  
- 既知の信頼されたユーザーの数によっては、すべてのメッセージを承認する必要があります。 メッセージの作成者、修理会社、および承認者のチェーン内の各信頼されたユーザーは一意である必要があります、同じユーザーできませんを作成または修復を承認または拒否メッセージ。 同じユーザーが複数を入力できませんを承認または却下マルチ ステップの承認プロセスで 1 つのメッセージを決定します。 独自に作成または修復されたメッセージを承認することはできません。 また、同じメッセージを複数の承認者として承認することができます。  
  
- 承認プロセス中にメッセージを変更することはできません (つまり、メッセージを元の送信メッセージの修復と新しいまたは修復のメッセージとしての New Submission の後に変更ことはできません)。  
  
- キー更新の検証ステージ中に変更されるメッセージは、元のメッセージ (作成または修復のいずれか) を正確に一致する必要があります。  
  
  このようなセキュリティのセマンティクスを適用するには、メッセージの修復 and New Submission 作成時または修復の申請プロセスの各段階で、受信したすべての XML メッセージに埋め込まれているデジタル署名を検証します。 Message Repair and New Submission のデジタル署名の検証は、次のチェックを実行します。 1 つ以上のこれらのチェック、Message Repair and New Submission の停止が失敗して、メッセージ ボックス セキュリティ障害からが永続化される場合は、イベント ログに記録されます。  
  
- XML メッセージでは、デジタル署名する必要があり、そのため、対応するデジタル署名を含める必要があります。  
  
- 信頼できるデジタル証明書を使用して、ワークフローで使用する各デジタル署名を行う必要があります。 これにより、メッセージの作成者、修理会社、検証、承認者が信頼されていること。  
  
- 各信頼されたデジタル証明書に属している必要があります、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]論理機関または内のアクションを実行する権限を持つドメイン グループのメンバーシップを持つドメイン ユーザー[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 これにより、作成または修復申請プロセスの各参加者は、正しい機関またはを実行する特定のアクションを実行する権限。  
  
   SharePoint サイトと、フォーム送信コードを使用してサイトのユーザー グループの Acl を上記の規則が適用されます。 ユーザーのメッセージに作用するではない場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ (ドメインまたはローカル)、Message Repair and New Submission はメッセージを拒否します。  
  
   たとえば、3 つのステージの承認プロセスを強制する組織がこれら 3 つの論理ロールを定義可能性があります: Repairers、検証方法 (キー更新ステージ)、および承認者。 同様に、ロールに参加しているユーザーに属している必要があります、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー ドメインのグループ。 SharePoint サイトをさらにロックダウンするには、(repairers、検証、承認者) などの論理ドメイン グループにユーザーを編成する必要があります。  
  
   サイトのユーザー グループの詳細については、次を参照してください。 [Windows SharePoint Services のセキュリティ](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)します。  
  
- スタック内の各のデジタル署名は、一意である必要があります。 つまり、(同じスタックで他の署名) を基準に、一意なデジタル証明書を使用して各デジタル署名を行う必要があります。 これによって、メッセージが、メッセージの作成/修復したユーザーが承認されていないことをユーザーには、同じメッセージを複数の承認者として承認なし。  
  
  Message Repair and New Submission メッセージの作成、修復、承認、および送信のインフラストラクチャのエントリ ポイントごとにチェックポイントすることで厳密なセキュリティ ポリシーが課されます。 これらのチェックポイントは Message Repair and New Submission のコア機能と緊密にし、回避することはできません。 Message Repair and New Submission とシームレスに統合するように設計中に、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム署名の機能もセキュリティで保護された信頼性と場合でも SWIFT メッセージの保護を適用するのに十分な堅牢なされるようにするために設計された[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]は使用されず、メッセージの送信メッセージの修復にエンドユーザーが直接、および New Submission 受信エンドポイント (SharePoint Web フォルダー)。