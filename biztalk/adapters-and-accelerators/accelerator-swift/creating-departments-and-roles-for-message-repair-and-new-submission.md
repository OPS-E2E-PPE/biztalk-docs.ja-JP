---
title: Message Repair and New Submission の部門とロールの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- departments, creating
- creating, roles
- roles, requirements
- roles, creating
- creating, departments
- certificates, messages
- messages, certificates
ms.assetid: 6337bd57-63c5-4d97-b558-ac27d5eb60d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21abbaa8b5e3b36dfb5ad9091afa0e05a6d807d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988883"
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a>Message Repair and New Submission の部門とロールを作成します。
Message Repair and New Submission 次の 4 つの異なる操作が含まれます。  
  
- 検証が失敗したメッセージの修復  
  
- 修復 (キーの更新を含む) の検証  
  
- 修復の承認  
  
- 新しいメッセージの作成  
  
  これらの操作のいずれかを実行するには、ユーザーは、操作に関連付けられているロールを想定する必要があります。 役割の処理部門の (後述) の一部である必要があります。 ワークフローのステージを実行した後に、メッセージを送信するには、ユーザー、ユーザーに関連付けられた有効な証明書メッセージに署名する必要があります。  
  
## <a name="creating-departments-and-roles"></a>部門とロールを作成します。  
 プロファイル Web クライアントのドキュメントを参照してください。  
  
## <a name="rules-of-role-use"></a>ロールの使用規則  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] ユーザー、ロール、および部門は、次の規則に従う必要があります。  
  
- 修復されたメッセージの完全なワークフローが、修復、検証、およびその後、メッセージを承認します。 作成されたメッセージの完全なワークフローが、作成、修復、検証、およびその後、メッセージを承認します。 検証と承認の手順は省略可能です。  
  
- 部門のワークフローは、ロールの作成または修復のロールを開始する必要があります。 ワークフローには、両方の作成と修復の手順 (作成されたメッセージのワークフロー) が含まれている場合、修復手順の直前に作成手順があります。  
  
- 作成されたメッセージのワークフローを作成する機能を持つ 1 つだけの役割を含める必要があります。  
  
- 各ワークフローは、修復の機能を持つロールが 1 つだけを含める必要があります。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが 1 つ以上のロールを関連付けることができますが、1 人のユーザーで実行できますない 1 つ以上の手順を 1 つのワークフロー。 たとえば、ユーザー A はメッセージを修復すると、ユーザー B がメッセージを検証、し、ユーザー A も B のユーザーを承認できますメッセージ。  
  
- その他の役割を基準とした RekeyVerify または承認の機能を持つ RekeyVerify または承認の機能を持つロールの順序のチェックはありません。  
  
- 修復が既にメッセージには、もう一度検証が失敗した場合に戻る MRSR サイト ドキュメント ライブラリの修復の受信トレイです。 この場合、(ワークフローの役割を実行したユーザーが既にに基づく) の検証と承認者のロールでは、以前の制限は適用されません。 たとえば、メッセージ、ユーザー B を A のユーザーの修復には、検証、およびユーザー A の修復でメッセージが拒否された場合メッセージし、ユーザー B は別のユーザーに、もう一度でしたメッセージを確認します。 場合は、ユーザー B がメッセージを承認します。 別の例されている場合、ユーザー A はメッセージを作成、ユーザー B は検証フェーズでメッセージを拒否、およびユーザー C は、メッセージを修復し、ユーザー A は、メッセージを確認できます。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証が失敗した場合、メッセージを作成するユーザーはそのメッセージを修復もできます。  
  
- のみ[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ワークフローに関連付けられている部門のユーザーはワークフローのステップを実行することができます。 ときに、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが、メッセージを送信する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージに関連付けられている部門のユーザーがロールを持っていることを確認します (ユーザー プロファイル (この場合、部門は、既定ではありません) web クライアントのプロファイルで)。  
  
- 管理者が、1 つを与える[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーの部門内の複数のロール。 1 人のユーザーには、修復、検証、承認、または作成、またはこれらのロールは、上記で説明した任意の 1 つのワークフローでの制限が適用の任意のサブセットを実行できます。  
  
## <a name="certificates"></a>証明書  
 修復、検証、承認、または、作成した後、ローカル コンピューター上のメッセージを送信する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが自分の証明書をメッセージに署名する必要があります。 証明書の作成の詳細については、[証明書のインストール](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)を参照してください。  
  
 修復、確認、承認、またはリモート クライアント コンピューターから MRSR サイトへのアクセス、メッセージを作成して、ユーザーは、(ユーザーが自身のクライアント コンピューターの現在のユーザー/個人/証明書ストアに証明書で自分の証明書を追加する必要があります。そのためには管理者である)。 さらに、サーバーの管理者する必要がありますユーザーの証明書 (および、クライアント コンピューターからサーバーにアクセスする他のユーザーの)、証明書を追加 (ローカル コンピューター)]、[その他のユーザー/証明書がサーバーに格納します。  
  
 1 人のユーザーは、いくつかの割り当てられたロールがあり、それらのロールのいずれかを実行するときに、同じ証明書を使用する必要があります。