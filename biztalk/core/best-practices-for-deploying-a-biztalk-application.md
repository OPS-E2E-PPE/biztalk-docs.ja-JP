---
title: BizTalk アプリケーションの展開のベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, deploying
- best practices, applications
- applications, best practices
- deploying, best practices
ms.assetid: 97ebf479-0dc5-4e95-b409-d3b6ad3d60d0
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03221335dcb41e8496c6808a8f20f0da364979ea
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529122"
---
# <a name="best-practices-for-deploying-a-biztalk-application"></a>BizTalk アプリケーション展開のベスト プラクティス
このトピックでは、BizTalk アプリケーションの展開のベスト プラクティスについて説明します。  
  
## <a name="group-related-artifacts-together-in-a-single-application"></a>1 つのアプリケーションで関連する成果物をグループ化します。  
 できるだけ多くの関連アイテムを、同じ BizTalk アプリケーションにまとめます。 こうすることで、複数のアイテムを 1 つのエンティティとして管理および展開できるようになり、管理が容易になります。 同じビジネス プロセスをサポートするアイテムや、類似の機能を実行するアイテムは、1 つのアプリケーションにグループ化できます。  
  
## <a name="deploy-shared-artifacts-in-a-separate-application"></a>別のアプリケーションで共有の成果物を配置します。  
 複数のアプリケーションで共有されるアイテムは、独立したアプリケーションで展開します。 たとえば、2 つのアプリケーションでスキーマを共有している場合は、そのスキーマを独立したアプリケーションに配置します。 これは、同じローカル一意識別子 (LUID)----成果物の名前と必要に応じてその他の属性で構成される複数のアイテムが BizTalk グループに存在できるためです。 場合は、1 つのアプリケーションにアイテムを含めるし、別のアプリケーションへの参照を作成し、成果物を含むアプリケーションを停止するときに正しく機能していないを参照するアプリケーションなどの問題が発生する可能性があります。  
  
 このベスト プラクティスは、種類が File としてアプリケーションに追加されるファイル アイテム (Readme ファイル、スクリプトなど) 以外の、すべての種類のアイテムに適用できます。 同じ名前を持つ 1 つ以上のファイル成果物は、BizTalk グループにデプロイできるためです。 したがって複数のアプリケーションで同じ名前のファイルを使用できるので、このベスト プラクティスは当てはまりません。 1 つのアプリケーションを停止しても、その他のアプリケーションに影響はありません。 ファイル アイテムを追加する方法の詳細については、次を参照してください。[アプリケーションにファイルを追加する方法](../core/how-to-add-a-file-to-an-application.md)します。  
  
 特定の成果物の種類の共有に関するベスト プラクティスについては、「別のアプリケーションで共有 Web サイトのデプロイ」を参照してください「デプロイは、別のアプリケーションでポリシーを共有」と、このセクションで「展開共有の別のアプリケーションで証明書」。  
  
## <a name="deploy-a-shared-web-site-in-a-separate-application"></a>別のアプリケーションで共有 Web サイトのデプロイします。  
 複数のビジネス アプリケーションで共有される Web サイトは、独立したアプリケーションで展開します。 この理由は、BizTalk アプリケーションをアンインストールすると、アプリケーションに含まれる Web サイトは実行中であっても削除されるためです。 削除した Web サイトが他のビジネス ソリューションと共有されていた場合、そのビジネス ソリューションは正常に機能しなくなります。  
  
## <a name="deploy-shared-policies-in-a-separate-application"></a>別のアプリケーションでの共有ポリシーを展開します。  
 複数のアプリケーションで使用されるポリシーは、1 つのアプリケーションから別のアプリケーションへの参照を作成せずに、独立したアプリケーションで展開します。 この理由は、アプリケーションを停止すると、そのアプリケーションのポリシーは展開解除されるためです。 他のアプリケーションで使用されているポリシーを含むアプリケーションを停止すると、どちらのアプリケーションでもポリシーは機能しなくなります。  
  
## <a name="deploy-shared-certificates-in-a-separate-application"></a>別のアプリケーションで共有証明書を展開します。  
 複数アプリケーションの送信ポートまたは受信ポートで使用される証明書は、独立したアプリケーションで展開します。その後、展開したアプリケーションに対し、その証明書を使用するアプリケーションから参照を作成します。 これは、複数のアイテムの luid ことができます、BizTalk グループに存在しないため、2 つのアプリケーションで同じ証明書をインポートすることはできませんので。 同じ証明書を使用する 2 つのアプリケーションをインポートしようとすると、最初のインポートは成功しますが、2 番目のインポートは成功しません。 [上書き] インポート オプションを使って既存の証明書を上書きしようとしても、その証明書は別のアプリケーションに含まれているため上書きできません。  
  
## <a name="never-deploy-an-assembly-from-visual-studio-on-a-production-computer"></a>実稼働コンピューターには、Visual Studio からアセンブリを展開できません。  
 開発の過程ではしばしば、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からのアセンブリの再展開が必要になります。 再展開を有効にする[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]展開解除、バインド解除、停止、およびアセンブリに含まれるアイテムの参加を解除することがあります。 これは開発環境では必要であり適切なことですが、実稼働環境では予期しない結果や結果や好ましくない結果を引き起こす可能性があります。 このためもからアセンブリを展開しようとしてすべてのユーザーの可能性を回避したり[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]実稼働コンピューターでは、インストールすること勧めすることはありません[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]実稼働コンピューター。  
  
 さらを参照しないでください、実稼働データベースを実行するコンピューターから[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
## <a name="when-deploying-large-msi-files-you-may-need-to-increase-the-default-transaction-timeout-of-the-com-components-used-by-biztalk-to-deploy-applications"></a>大きな MSI ファイルを展開する場合は、BizTalk アプリケーションをデプロイするため、COM + コンポーネントの既定のトランザクション タイムアウトを増加する必要があります。  
 展開する MSI ファイルが非常に大きい場合 (100 MB を超える) アプリケーションの展開中に、BizTalk で使用される COM + コンポーネントの既定のトランザクション タイムアウト内でアプリケーションを展開しない可能性があります。 デプロイが完了する前に、トランザクションに関連付けられたこれら COM + コンポーネントがタイムアウトする場合、デプロイは失敗します。 非常に大きなを展開する場合、MSI ファイルがこの問題を軽減するためにこれらのアプローチの 1 つを検討します。  
  
1.  1 つの大きな MSI ファイルの代わりにいくつかの小さな MSI ファイルをデプロイします。  
  
2.  関連付けられている 3,000 秒の既定のトランザクション タイムアウト値を増やし、 **Microsoft.BizTalk.ApplicationDeployment.Group**と**Microsoft.BizTalk.Deployment.DeployerComponent**内のコンポーネント、**コンポーネント サービス**管理インターフェイスです。 属しているこれらのコンポーネント、 **Microsoft.BizTalk.ApplicationDeployment.Engine**と**Microsoft.Biztalk.Deployment** COM + アプリケーションそれぞれします。 詳細については、トランザクションを変更する方法についての COM + コンポーネントのタイムアウト値を参照してください[MTS または COM + のトランザクションのタイムアウト値を変更する方法](http://go.microsoft.com/fwlink/?LinkId=67691)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md)