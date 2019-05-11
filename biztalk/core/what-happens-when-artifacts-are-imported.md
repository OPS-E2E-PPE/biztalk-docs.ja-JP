---
title: アイテムのインポート時の動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing, artifacts
- artifacts, importing
ms.assetid: a83957df-6e16-419a-b693-87985b498cc4
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52098eaa69fd2cefc25e6c7ba27908ec6a5a9bd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395173"
---
# <a name="what-happens-when-artifacts-are-imported"></a>アイテムのインポート時の動作
このトピックでは、インポートされたアイテムの処理について説明します。 このトピックで説明されている成果物をインポートする次の 3 つの方法はあります。  
  
-   BizTalk グループまたはアプリケーションに BizTalk の .msi ファイル内のアイテムをインポートします。  
  
-   .Xml ポリシー ファイルを BizTalk グループにインポートします。  
  
-   BizTalk グループまたはアプリケーションにバインド ファイルのインポート  
  
## <a name="importing-a-biztalk-msi-file"></a>BizTalk .msi ファイルをインポートします。  
 BizTalk グループまたはアプリケーションに BizTalk の .msi ファイルをインポートすると、BizTalk Server は、次のように含まれるアイテムを処理します。  
  
-   インポート中には、グループ内の他のアプリケーションには、このアプリケーションからの参照が追加された場合、参照は、BizTalk 管理データベースに追加されます。  
  
-   このオプションを指定した場合、アプリケーションの既存のアイテムが同じ完全名とバージョン番号 (該当する場合) が .msi ファイル内のアイテムで上書きされます。  
  
-   アプリケーションに追加されたバインド ファイルのインポート中に、ターゲット環境を選択した場合は、バインドが適用されます。  
  
-   インポート時に実行するように構成する前または処理後のスクリプトが実行されます。  
  
-   成果物のファイル ベースのデータがシリアル化され、BizTalk 管理データベースに格納されています。 これには、アセンブリ、仮想ディレクトリ、ファイル、スクリプト、証明書、および BAM アイテムのデータが含まれます。  
  
    > [!IMPORTANT]
    >  セキュリティ上の理由から、秘密キーは、エクスポートされるときに各証明書から削除されます。 そのため、BizTalk 管理データベースに秘密キーは格納されません。  
  
-   ポリシー データは、ルール エンジン データベースに格納されます。  
  
-   BAM アイテムは、BAM プライマリ インポート データベースに格納されます。 BAM 定義を展開します。  
  
-   BizTalk アセンブリと"インポート時に GAC に追加 の展開オプションを構成する .NET アセンブリは、グローバル アセンブリ キャッシュ (GAC) に追加されます。  
  
> [!NOTE]
>  BizTalk Server がアプリケーションに関連付けられているすべての構成情報とデータのデータベースから取得できます後でアプリケーションを .msi ファイルをエクスポートするときに、BizTalk Server データベースのアイテムのデータが格納されているため、成果物、.msi ファイルに含めます。 .Msi ファイルを別の BizTalk グループにインポートしたすべての成果物の構成情報とデータが新しいグループに再作成されます。  
  
 アプリケーションをインポートした後は、表示して管理、および 1 つのエンティティとしてグループ化または個別に管理コンソールまたは BTSTask を使用して、アプリケーションで成果物を配置できます。 詳細については、次を参照してください。[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)します。  
  
## <a name="importing-a-policy"></a>ポリシーのインポート  
 .Xml ファイルからポリシーをインポートすると、ポリシーがルール エンジン データベースに追加されます。 BizTalk .msi ファイル内のポリシーをインポートするとは異なり、ポリシーは、BizTalk 管理データベース内の任意のアプリケーションに関連付けられていません。 [ポリシー] ノードで、ポリシーが表示されます、\<すべての成果物\>BizTalk Server 管理コンソール内のフォルダー。 ポリシーをインポートした後で、グループを使用するアプリケーションの使用可能にすることを発行できます。 詳細については、次を参照してください。[ポリシーの管理](../core/managing-policies.md)します。  
  
## <a name="importing-a-binding-file"></a>バインド ファイルのインポート  
 バインド ファイルを BizTalk グループにインポートして、インポートされたファイルのバインドと同じ名前を持つグループに現在存在するすべてのバインドは、インポートされたファイルのバインドで上書きされます構成が適用されます。  
  
 ファイルをインポートするバインドを BizTalk アプリケーションにも個別にまたはアプリケーションの一部として、すべてのバインドされているアプリケーション内に存在ファイルのバインドはインポートされたバインディングによって上書きされますと、同じ名前を持つときに、構成が適用されます。  
  
> [!IMPORTANT]
>  セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。 バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。 BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。 手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。 参照してください[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)します。  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)