---
title: BizTalk Server ランタイムのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, runtime
- runtime, security
- discretionary access control lists (DACLs)
- DACLs
- .NET Framework Code Access Security Mechanism
ms.assetid: 1933789d-b79a-47ad-8f70-6f1e99bc2be0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1e452a7cf78f63ac128064620db3084e91946fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357871"
---
# <a name="biztalk-server-runtime-security-recommendations"></a>BizTalk Server ランタイムのセキュリティに関する推奨事項
メッセージの受信、送信、処理、および追跡を行うすべてのコンピューターに BizTalk Server ランタイム (エンジン) をインストールする必要があります。 つまり、BizTalk ホスト インスタンス (処理サーバー) を作成するコンピューターにランタイム コンポーネントをインストールする必要があります。 BizTalk Server ランタイムをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
- BizTalk Server ランタイム タスクを行う最小セキュリティのユーザー権利が付与されていることを確認します。 最低限のセキュリティ ユーザー権限の詳細については、次を参照してください。[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)します。  
  
  > [!NOTE]
  >  BizTalk 構成は、タスクを行うための最小限のアクセス権限をアカウントに与えます。  
  
- 各ホスト インスタンスのサービス アカウントを使用して、ホスト インスタンスを実行するコンピューターのサービス権限としてログオンする必要があります。  
  
- ホストのサービス アカウントだけがホストに関連するメッセージ ボックス データにアクセスできます。また、これらのサービスだけがメッセージ ボックスに送信できます。 情報の漏えいの可能性を最小限に抑えるため、複数のホストで同じサービス アカウントを使用しないでください。  
  
- 処理サーバー (追跡を行わないホスト) は、メッセージ ボックス データベース、管理データベース、およびマスター シークレット サーバーにのみ接続する必要があります。 インターネット プロトコル セキュリティ (IPsec) を使用すると、処理サーバーのアクセスをこれらの 2 つのデータベースとマスター シークレット サーバーに制限できます。  
  
- 同じ BizTalk ホスト内で実行されるすべてのコンポーネントは、ホストと同じ信頼レベルを持ちます。 同じホストで実行する必要がある (同じ信頼レベルで共有する必要がある) コンポーネントを決めるのは、BizTalk 管理者の責任です。 BizTalk は、BizTalk 管理者がインストールしたアセンブリだけが BizTalk ホストで実行されていることを確認します。 BizTalk が使用するアセンブリに関する制限を追加する場合 (たとえば、特定のベンダーによって署名されたアセンブリだけを実行するように BizTalk を制限する場合やオーケストレーションに対する厳密な名前の署名を検証する場合)、[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] コード アクセス セキュリティ メカニズムを使用できます。 Microsoft MSDN Web サイトの詳細については[ http://go.microsoft.com/fwlink/?LinkId=60947](http://go.microsoft.com/fwlink/?LinkId=60947)します。  
  
- メッセージを送信する場合の認証の細かさは、BizTalk ホスト レベルです。 つまり、同じ BizTalk ホスト内で実行されているオーケストレーションまたはアダプターが複数ある場合、ホストに送信されるメッセージを受信するオーケストレーションを特定の 1 つのオーケストレーションに制限することはできません。  
  
- ホストにメッセージを受信する権限がない場合、保留キューにメッセージが配置されます。 既定で、受信アダプターとオーケストレーションが同じホストで実行されている場合、オーケストレーションは、ホストの保留キューを読み込むことができます。 認証失敗により BizTalk が保留したメッセージをオーケストレーションが取得する可能性があります。 このため、同じホストでオーケストレーションと受信アダプターを実行しないことをお勧めします。  
  
- ホスト インスタンスは、特定のコンピューターで実行される Windows サービスです。 ホスト インスタンスを作成するには、BizTalk 管理者と先ホスト インスタンスを作成するように BizTalk ホスト インスタンスに対応する Windows サービスを作成するコンピューターの Windows 管理者の両方があります。  
  
- Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でアセンブリを生成すると、統合開発環境 (IDE) によって生成されるカスタム キーが使用されます。 特定のキーですべてのアセンブリの署名が必要な環境を使用している場合、キーを使用するためにすべての開発用コンピューターに IDE を構成するか、アセンブリの遅延署名を利用する必要があります。  
  
- 受信パイプラインと送信パイプラインのすべてのコンポーネントは、メモリの使用量を抑えようとします。 特定のしきい値よりもデータが大きい場合、これらのコンポーネントは、一時フォルダー (%TEMP%) のディスクにデータをストリーム出力します。 サービス アカウントだけを使用してこれらのファイルを読み込むため、適切な随意アクセス制御リスト (DACL) がホスト インスタンス用のサービス アカウントの一時フォルダーに格納されていることを確認する必要があります。 また、大きなファイルに備えて予備の領域を一時フォルダーに確保する必要があります。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)   
 [処理サーバーのポート](../core/ports-for-the-processing-servers.md)   
 [BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md)   
 [セキュリティの計画](../core/planning-for-security.md)