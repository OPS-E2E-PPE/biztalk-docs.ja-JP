---
title: "Message Repair and New Submission の部門とロールの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d033ab3910657373f6e48b1f6e6bed076f730b51
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-departments-and-roles-for-message-repair-and-new-submission"></a>Message Repair and New Submission の部門とロールの作成
Message Repair and New Submission には、次の 4 つの異なる操作が含まれます。  
  
-   検証が失敗したメッセージの修復  
  
-   修復 (キー更新を含む) の検証  
  
-   修復の承認  
  
-   新しいメッセージの作成  
  
 これらの操作のいずれかを実行するには、ユーザーは、操作に関連付けられている役割を想定する必要があります。 ロールは、処理部門の (後述) の一部もあります。 をワークフローにステージを実行した後、メッセージを送信するには、ユーザー、ユーザーに関連付けられた有効な証明書メッセージに署名する必要があります。  
  
## <a name="creating-departments-and-roles"></a>部門とロールの作成  
 プロファイルの Web クライアントのドキュメントを参照してください。  
  
## <a name="rules-of-role-use"></a>ロールの使用の規則  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー、ロール、および部門は、次の規則に従う必要があります。  
  
-   修復されたメッセージの完全ワークフローでは、修復、検証、およびメッセージを承認します。 作成したメッセージの完全ワークフローでは、作成、修復、検証、およびメッセージを承認します。 検証と承認の手順は省略できます。  
  
-   部門のワークフローは、ロールの作成または修復のロールで始まる必要があります。 ワークフローには、作成と修復の両方の手順 (のワークフローを作成したメッセージ) が含まれている場合、修復手順の直前に作成する手順を引き起こすことがあります。  
  
-   作成したメッセージのワークフローを作成する機能を持つ 1 つだけの役割を含める必要があります。  
  
-   各ワークフローでは、修復の機能を持つ 1 つだけの役割を含める必要があります。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、複数のロールを関連付けることができますが、1 人のユーザーはも実行されない 1 つ以上の手順で 1 つのワークフローです。 たとえば、ユーザー A はメッセージを修復すると、ユーザー B がメッセージを検証、し、ユーザー A も B のユーザーを承認できますメッセージ。  
  
-   その他のロール基準とした RekeyVerify または承認の機能を持つ RekeyVerify または承認の機能を持つロールの順序のチェックはありません。  
  
-   既にに修復をメッセージには、もう一度検証が失敗した場合に戻る MRSR サイト ドキュメント ライブラリで修復の受信トレイです。 この場合、(ワークフロー内のロールを実行したユーザーが既にに基づいた) の検証および承認者の役割は、以前の制限は適用されません。 たとえば、メッセージ、ユーザー B のユーザー A 修復検証、およびユーザー A の修復でメッセージを拒否した場合は、メッセージし、ユーザー B は別のユーザーに、もう一度でしたメッセージを確認します。 場合は、ユーザー B の間でメッセージが承認可能性があります。 別の例です。 ユーザー A がメッセージを作成し、ユーザー B は、検証でメッセージを拒否し、ユーザー C は、メッセージを修復し、ユーザー A はメッセージを確認できます。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証が失敗した場合、メッセージを作成したユーザーはそのメッセージを修復もできます。  
  
-   のみ[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ワークフローに関連付けられている部門のユーザーには、ワークフローで、手順を実行できます。 ときに、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーは、メッセージを送信する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージに関連付けられている部門のユーザーがロールを持っていることを確認 (を通じて、ユーザー プロファイル (この場合、部門は、既定ではありません) にプロファイル web クライアント)。  
  
-   管理者は、1 つを移すことができる[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーの部門内の複数の役割です。 1 人のユーザーには、修復、検証、承認、または作成、またはそれらのロールは、上記で説明した任意の 1 つのワークフローでの制限が適用の任意のサブセットを実行できます。  
  
## <a name="certificates"></a>証明書  
 修復、検証、承認、または、作成した後、ローカル コンピューター上のメッセージを送信する、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーが自分の証明書をメッセージに署名する必要があります。 証明書の作成の詳細については、次を参照してください。[証明書のインストール](../../adapters-and-accelerators/accelerator-swift/installing-certificates.md)です。  
  
 修復、ことを確認、承認、またはリモート クライアント コンピューターから MRSR サイトへのアクセス、メッセージを作成するには、ユーザーは、(ユーザーが、クライアント コンピューターの現在のユーザー/個人/証明書ストアに証明書で、ユーザー証明書を追加する必要があります。そのためには管理者である)。 さらに、サーバーの管理者である必要がありますユーザーの証明書 (および追加、クライアント コンピューターから、サーバーにアクセスできる他のユーザーの) 証明書 (ローカル コンピューター) に/その他のユーザー/証明書がサーバーに格納します。  
  
 1 人のユーザーは、いくつかの割り当てられた役割があり、これらのロールのいずれかを実行するときに、同じ証明書を使用する必要があります。