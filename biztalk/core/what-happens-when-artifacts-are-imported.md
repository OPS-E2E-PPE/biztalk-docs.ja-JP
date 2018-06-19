---
title: アイテムのインポート時の動作 |Microsoft ドキュメント
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
ms.openlocfilehash: aa252b520f985667820861403a46d39c8527ea07
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974912"
---
# <a name="what-happens-when-artifacts-are-imported"></a>アイテムのインポート時の動作
このトピックでは、アイテムがインポートされるときの動作について説明します。 アイテムのインポートには次の 3 つの方法があり、ここではそれぞれについて説明します。  
  
-   BizTalk .msi ファイル内のアイテムを BizTalk グループまたはアプリケーションにインポートする。  
  
-   .xml ポリシー ファイルを BizTalk グループにインポートする。  
  
-   バインド ファイルを BizTalk グループまたはアプリケーションにインポートする。  
  
## <a name="importing-a-biztalk-msi-file"></a>BizTalk .msi ファイルのインポート  
 BizTalk .msi ファイルを BizTalk グループまたはアプリケーションにインポートすると、そのファイルに含まれているアイテムが BizTalk Server で次のように処理されます。  
  
-   インポート時にこのアプリケーションからグループ内の他のアプリケーションへの参照を追加した場合は、その参照が BizTalk 管理データベースに追加されます。  
  
-   このオプションを指定すると、アプリケーション内の既存のアイテムが、完全な名前とバージョン番号 (該当する場合) が同じである .msi ファイル内のアイテムで上書きされます。  
  
-   アプリケーションにバインド ファイルが追加されている場合に、インポート時にそのファイルのターゲット環境を選択すると、それらのバインドが適用されます。  
  
-   インポート時に実行されるように構成されている処理前または処理後のスクリプトが実行されます。  
  
-   ファイルベースのアイテム データがシリアル化され、BizTalk 管理データベースに格納されます。 これには、アセンブリ、仮想ディレクトリ、ファイル、スクリプト、証明書、および BAM アイテムのデータが含まれます。  
  
    > [!IMPORTANT]
    >  セキュリティ上の理由により、各証明書の秘密キーはエクスポート時に削除されます。 したがって、BizTalk 管理データベースには秘密キーが格納されません。  
  
-   ポリシー データがルール エンジン データベースに格納されます。  
  
-   BAM アイテムが BAM プライマリ インポート データベースに格納されます。 BAM 定義が展開されます。  
  
-   "MSI ファイル インポートのグローバル アセンブリ キャッシュに追加します" 展開オプションが設定されている BizTalk アセンブリと .NET アセンブリが、グローバル アセンブリ キャッシュ (GAC) に追加されます。  
  
> [!NOTE]
>  アイテム データは BizTalk Server のデータベースに格納されるため、後からアプリケーションを .msi ファイルにエクスポートしたときに、BizTalk Server はアプリケーションとそのアイテムに関連するすべての構成情報とデータをこれらのデータベースから取得し、.msi ファイルに取り込むことができます。 .msi ファイルを別の BizTalk グループにインポートすると、すべてのアイテム構成情報とデータが新しいグループで再作成されます。  
  
 アプリケーションをインポートした後に、管理コンソールまたは BTSTask を使用して、アプリケーション内のアイテム全体を 1 つのエンティティとして、または各アイテムを個別に、表示、管理、展開できます。 詳細については、次を参照してください。[アプリケーションの展開と管理ツール](../core/application-deployment-and-management-tools.md)です。  
  
## <a name="importing-a-policy"></a>ポリシーのインポート  
 .xml ファイルからポリシーをインポートすると、そのポリシーがルール エンジン データベースに追加されます。 BizTalk .msi ファイル内のポリシーをインポートする場合とは異なり、ポリシーは BizTalk 管理データベース内のどのアプリケーションにも関連付けられません。 [ポリシー] ノードで、ポリシーが表示されます、\<すべての成果物\>BizTalk Server 管理コンソール内のフォルダーです。 インポートしたポリシーは、グループ内のアプリケーションが使用できるように公開できます。 詳細については、次を参照してください。[ポリシーの管理](../core/managing-policies.md)です。  
  
## <a name="importing-a-binding-file"></a>バインド ファイルのインポート  
 バインド ファイルを BizTalk グループにインポートすると、そのファイル内のバインドによって、グループ内でそれらのバインドと同じ名前を持つ既存のバインドがすべて上書きされ、構成が適用されます。  
  
 バインド ファイルを BizTalk アプリケーションに個別にインポートするか、またはアプリケーションの一部としてインポートすると、そのファイル内のバインドによって、アプリケーション内でそれらのバインドと同じ名前を持つバインドがすべて上書きされ、構成が適用されます。  
  
> [!IMPORTANT]
>  セキュリティ上の理由により、BizTalk Server では、バインド ファイルのエクスポート時にバインドのパスワードがファイルから削除されます。 バインドをインポートした後で、送信ポートと受信場所のパスワードを再構成する必要があります。 BizTalk Server 管理コンソールの [トランスポートのプロパティ] ダイアログ ボックスで、送信ポートと受信場所のパスワードをそれぞれ構成します。 手順については、次を参照してください。[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。 関連項目[を作成する方法、受信場所](../core/how-to-create-a-receive-location.md)です。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開時の成果物を処理します。](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [BizTalk アプリケーション、バインド、およびポリシーをインポートします。](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)