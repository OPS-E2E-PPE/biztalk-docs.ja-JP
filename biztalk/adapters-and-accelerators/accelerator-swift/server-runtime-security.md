---
title: "Server ランタイム セキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, server runtime
- servers, security
- servers, runtime
ms.assetid: 40f5ca3e-d9d3-4543-bd38-82283c343b76
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5979162a521185b87977191c9d709fb754b1ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="server-runtime-security"></a>Server ランタイムのセキュリティ
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Message Repair and New Submission は、セキュリティで保護された、決定的な方法でビジネス ユーザー、バックエンド システム、および SWIFT ネットワーク エンドポイント間で SWIFT メッセージのフローを制御します。 ビジネス ユーザーによって送信されたメッセージを認証し、メッセージのデータおよびビジネス ルールの正確性を検証してから、バックエンド システムをまたはに SWIFT ネットワークは、最終的な配信のためにメッセージをルーティングします。 デジタル証明書の詳細についてを参照してください「の暗号化および署名証明書」、MSDN ライブラリの Web サイトにある[http://go.microsoft.com/fwlink/?linkid=50285](http://go.microsoft.com/fwlink/?linkid=50285)です。  
  
 Message Repair and New Submission は、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]オーケストレーション アプリケーションでホストされ、実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ コンテキスト。 としてセキュリティで保護された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]によってアプリケーション、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]前に説明したセキュリティ機能です。 Message Repair and New Submission もを定義し、次のように SWIFT メッセージの作成、修復、承認、および送信、固有のユーザー レベルのセキュリティ ポリシーを適用します。  
  
-   新しいまたは修復された、すべてのメッセージが送信された[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]経由の Message Repair and New Submission が、信頼されたユーザーから送信する必要があります。  
  
-   作成またはメッセージを修復する信頼されたユーザーは、正しい認証および権限が必要です。 信頼済みのユーザーを承認または拒否のメッセージは、正しい認証および権限が必要です。  
  
-   すべてのメッセージは、信頼されたユーザーの数が承認する必要があります。 メッセージの作成者、修理会社、および承認者のチェーン内の各信頼されたユーザーを一意にする必要があります、同じユーザーを作成または修復し承認または却下できませんメッセージ。 同じユーザーが複数を入力できませんを承認または却下、複数の手順の承認プロセスで 1 つのメッセージを決定します。 複数の承認者として、同じメッセージを承認することができます。 また、独自に作成された、または修復されたメッセージを承認することはできません。  
  
-   承認プロセス中にメッセージを変更することはできません (つまり、メッセージをメッセージ修復するには元の送信と、新規または修復されたメッセージとして、New Submission の後に変更できません)。  
  
-   キーの再検証ステージ中に変更されたメッセージは、元のメッセージ (作成または修復のいずれか) を正確に一致する必要があります。  
  
 セマンティクスを強制的にこれらのセキュリティ、メッセージの修復 and New Submission、作成や修復承認送信プロセスの各段階で、受信したすべての XML メッセージに埋め込まれているデジタル署名を検証します。 Message Repair and New Submission のデジタル署名の検証では、次のチェックを実行します。 1 つ以上のこれらのチェック失敗 Message Repair and New Submission を停止し、メッセージ ボックスと、セキュリティ エラーが永続化される場合は、イベント ログに記録されます。  
  
-   XML メッセージでは、デジタル署名する必要があり、そのため、対応するデジタル署名を含める必要があります。  
  
-   信頼できるデジタル証明書を使用して、ワークフローで使用する各デジタル署名を行う必要があります。 これにより、メッセージの作成者、修理会社、検証、承認者が信頼されていること。  
  
-   各信頼できるデジタル証明書に属している必要があります、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]論理機関または内のアクションを実行する権限を持つドメイン グループのメンバーシップを持つドメイン ユーザー[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 これにより、作成または修復申請プロセスの各参加者は、適切な権限、あるいはそれらが実行する特定の操作を実行すること。  
  
     サイト ユーザー グループと、フォーム送信コードを通じて、SharePoint サイト上の Acl を介して、上記の規則が適用されます。 メッセージに作用するユーザーに含まれていない場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ (ドメインまたはローカル)、Message Repair and New Submission はメッセージを拒否します。  
  
     たとえば、3 つのステージの承認プロセスを強制する組織を定義これら 3 つの論理ロール: Repairers、検証方法 (キー更新ステージ)、および承認者。 ロールに参加しているユーザーが同じように属している必要があります、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー ドメインのグループです。 SharePoint サイトを遮断するには、(repairers、検証方法、承認者) などの論理ドメイン グループにユーザーを編成する必要があります。  
  
     サイト ユーザー グループの詳細については、次を参照してください。 [Windows SharePoint Services のセキュリティ](../../adapters-and-accelerators/accelerator-swift/windows-sharepoint-services-security.md)です。  
  
-   スタック内の各のデジタル署名は、一意である必要があります。 つまり、(他のシグネチャに、同じスタック) への相対固有のデジタル証明書を使用して各デジタル署名を行う必要があります。 これにより、メッセージが、メッセージの作成/修復するユーザーが承認されていないユーザーに複数の承認者として、同じメッセージが承認されていないこと。  
  
 Message Repair and New Submission メッセージの作成、修復、承認、および送信のインフラストラクチャへの各エントリ ポイントにチェックポイントが使用して厳密なセキュリティ ポリシーが適用されます。 これらのチェックポイントは、Message Repair and New Submission のコア機能と密接に結び付いているし、回避することはできません。 Message Repair and New Submission とシームレスに統合するように設計中に、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォーム署名の機能では、安全性と信頼性と場合でも SWIFT メッセージの保護を適用するのに十分な堅牢にも設計されています[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]は使用されず、およびメッセージの送信メッセージの修復するにはエンドユーザーによる直接 New Submission 受信エンドポイント (SharePoint Web フォルダー)。