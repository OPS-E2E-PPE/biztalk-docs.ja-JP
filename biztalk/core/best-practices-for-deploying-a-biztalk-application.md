---
title: "BizTalk アプリケーションを配置するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, deploying
- best practices, applications
- applications, best practices
- deploying, best practices
ms.assetid: 97ebf479-0dc5-4e95-b409-d3b6ad3d60d0
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b50ff0a6e64633090e562b6ca8e3ae66eb8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-deploying-a-biztalk-application"></a>BizTalk アプリケーション展開のベスト プラクティス
ここでは、BizTalk アプリケーションを展開するときのベスト プラクティスについて説明します。  
  
## <a name="group-related-artifacts-together-in-a-single-application"></a>関連アイテムを 1 つのアプリケーションにグループ化する  
 できるだけ多くの関連アイテムを、同じ BizTalk アプリケーションにまとめます。 こうすることで、複数のアイテムを 1 つのエンティティとして管理および展開できるようになり、管理が容易になります。 同じビジネス プロセスをサポートするアイテムや、類似の機能を実行するアイテムは、1 つのアプリケーションにグループ化できます。  
  
## <a name="deploy-shared-artifacts-in-a-separate-application"></a>共有アイテムを独立したアプリケーションで展開する  
 複数のアプリケーションで共有されるアイテムは、独立したアプリケーションで展開します。 たとえば、2 つのアプリケーションでスキーマを共有している場合は、そのスキーマを独立したアプリケーションに配置します。 この理由は、BizTalk グループ内で複数のアイテムに同じローカル一意識別子 (LUID) を使用できないためです (ローカル一意識別子はアイテム名と、省略可能なその他の属性から成ります)。 アイテムを 1 つのアプリケーションに含め、別のアプリケーションからそのアイテムへの参照を作成した場合は、アイテムが含まれるアプリケーションを停止すると、そのアイテムを参照するアプリケーションが正しく機能しなくなるなどの問題が発生する可能性があります。  
  
 このベスト プラクティスは、種類が File としてアプリケーションに追加されるファイル アイテム (Readme ファイル、スクリプトなど) 以外の、すべての種類のアイテムに適用できます。 ファイル アイテムは、BizTalk グループ内に同じ名前で複数展開でき、 したがって複数のアプリケーションで同じ名前のファイルを使用できるので、このベスト プラクティスは当てはまりません。 1 つのアプリケーションを停止しても、他のアプリケーションには影響しません。 ファイル アイテムの追加の詳細については、次を参照してください。[ファイルをアプリケーションに追加する方法](../core/how-to-add-a-file-to-an-application.md)です。  
  
 特定種類のアイテムの共有に関するベスト プラクティスについては、後の「共有 Web サイトを独立したアプリケーションで展開する」、「共有ポリシーを独立したアプリケーションで展開する」、および「共有証明書を独立したアプリケーションで展開する」を参照してください。  
  
## <a name="deploy-a-shared-web-site-in-a-separate-application"></a>共有 Web サイトを独立したアプリケーションで展開する  
 複数のビジネス アプリケーションで共有される Web サイトは、独立したアプリケーションで展開します。 この理由は、BizTalk アプリケーションをアンインストールすると、アプリケーションに含まれる Web サイトは実行中であっても削除されるためです。 削除した Web サイトが他のビジネス ソリューションと共有されていた場合、そのビジネス ソリューションは正常に機能しなくなります。  
  
## <a name="deploy-shared-policies-in-a-separate-application"></a>共有ポリシーを独立したアプリケーションで展開する  
 複数のアプリケーションで使用されるポリシーは、1 つのアプリケーションから別のアプリケーションへの参照を作成せずに、独立したアプリケーションで展開します。 この理由は、アプリケーションを停止すると、そのアプリケーションのポリシーは展開解除されるためです。 他のアプリケーションで使用されているポリシーを含むアプリケーションを停止すると、どちらのアプリケーションでもポリシーは機能しなくなります。  
  
## <a name="deploy-shared-certificates-in-a-separate-application"></a>共有証明書を独立したアプリケーションで展開する  
 複数アプリケーションの送信ポートまたは受信ポートで使用される証明書は、独立したアプリケーションで展開します。その後、展開したアプリケーションに対し、その証明書を使用するアプリケーションから参照を作成します。 この理由は、BizTalk グループ内で複数のアイテムに同じ LUID を使用できないためです。したがって、2 つの異なるアプリケーションの同じ証明書をインポートすることはできません。 同じ証明書を使用する 2 つのアプリケーションをインポートしようとすると、最初のインポートは成功しますが、2 番目のインポートは成功しません。 [上書き] インポート オプションを使って既存の証明書を上書きしようとしても、その証明書は別のアプリケーションに含まれているため上書きできません。  
  
## <a name="never-deploy-an-assembly-from-visual-studio-on-a-production-computer"></a>実稼働コンピューターの Visual Studio からアセンブリを展開しない  
 開発の過程ではしばしば、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からのアセンブリの再展開が必要になります。 再展開を可能にするため、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ではアセンブリに含まれるアイテムの展開解除、バインド解除、停止、および参加解除が行われます。 これは開発環境では必要であり適切なことですが、実稼働環境では予期しない結果や結果や好ましくない結果を引き起こす可能性があります。 この理由から、実稼働コンピューター上の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からはアセンブリを展開できないようにしてください。実稼働コンピューターには [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] をインストールしないことをお勧めします。  
  
 また、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を実行しているコンピューターからは実稼働データベースを参照しないでください。  
  
## <a name="when-deploying-large-msi-files-you-may-need-to-increase-the-default-transaction-timeout-of-the-com-components-used-by-biztalk-to-deploy-applications"></a>大きなサイズの MSI ファイルを展開する場合、アプリケーションを展開するには BizTalk で使用される COM+ コンポーネントの既定のトランザクション タイムアウトを大きくする必要がある場合があります。  
 展開する MSI ファイルのサイズが非常に大きい (100 MB 以上) 場合は、展開時に BizTalk で使用される COM+ コンポーネントの既定のトランザクション タイムアウトまでにアプリケーションの展開が完了しない場合があります。 展開が完了する前に COM+ コンポーネント関連のトランザクションがタイムアウトになると、展開は失敗します。 非常に大きなサイズの MSI ファイルを展開する場合は、この問題を緩和するため、次のいずれかの方法を使用することを検討してください。  
  
1.  1 つの大きな MSI ファイルを展開するのではなく、複数の小さな MSI ファイルを展開する。  
  
2.  関連付けられている 3,000 秒の既定のトランザクション タイムアウトを増やす、 **Microsoft.BizTalk.ApplicationDeployment.Group**と**Microsoft.BizTalk.Deployment.DeployerComponent**内のコンポーネント、**コンポーネント サービス**管理インターフェイスです。 これらのコンポーネントが属している、 **Microsoft.BizTalk.ApplicationDeployment.Engine**と**Microsoft.Biztalk.Deployment** COM + アプリケーションそれぞれします。 トランザクションを変更する方法の詳細については、COM + コンポーネントのタイムアウト値を参照してください[MTS または COM + のトランザクション タイムアウト値を変更する方法](http://go.microsoft.com/fwlink/?LinkId=67691)です。  
  
## <a name="see-also"></a>参照  
 [展開して、BizTalk アプリケーションの管理](../core/deploying-and-managing-biztalk-applications.md)