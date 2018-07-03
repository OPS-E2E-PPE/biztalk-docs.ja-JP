---
title: アイテムのエクスポート時の動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exporting, artifacts
- artifacts, exporting
ms.assetid: accc9a81-01fb-4da7-a5a5-167835d393a2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4a4b83608c09ff08fd8536bcdac806e3299775b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977323"
---
# <a name="what-happens-when-artifacts-are-exported"></a>アイテムのエクスポート時の動作
このトピックでは、アイテムがエクスポートされるときの動作について説明します。 アイテムのエクスポートには次の 3 つの方法があり、ここではそれぞれについて説明します。  
  
-   BizTalk アプリケーションとそのアイテムを BizTalk .msi (Windows インストーラー) ファイルにエクスポートする  
  
-   ポリシーを .xml ファイルにエクスポートする  
  
-   バインドを .xml ファイルにエクスポートする  
  
## <a name="exporting-a-biztalk-application"></a>BizTalk アプリケーションをエクスポートします。  
 BizTalk アプリケーションとそれに含まれるアイテムをエクスポートすると、アプリケーションの構成情報とアイテム データが BizTalk の .msi ファイルにエクスポートされます。 ほとんどのアイテム データは BizTalk 管理データベースからエクスポートされますが、次の例外があります。  
  
- ポリシー データは、グループのルール エンジン データベースからエクスポートされます。  
  
- 仮想ディレクトリのデータは、管理データベースにない場合は、インターネット インフォメーション サービス (IIS) メタベースからエクスポートされます。 仮想ディレクトリが明示的に追加されていないアプリケーションと、ケースになります (」の説明に従って[仮想ディレクトリをアプリケーションに追加する方法](../core/how-to-add-a-virtual-directory-to-an-application.md)) またはアプリケーションが .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされました。  
  
- 証明書データは、管理データベースにない場合は、ローカル コンピューター上の "その他のユーザー" 証明書ストアからエクスポートされます。 証明書が明示的に追加されていないアプリケーションと、ケースになります (」の説明に従って[アプリケーションに証明書を追加する方法](../core/how-to-add-a-certificate-to-an-application.md)) またはアプリケーションがされた .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされます。 アプリケーションを証明書が関連付けられている受信ポートと共にエクスポートすると、証明書がエクスポートされます。 エクスポートでは、秘密キーは証明書から削除されます。  
  
  この .msi ファイルを使用して、アプリケーションのアイテムとそのすべてのデータを、別の BizTalk グループのアプリケーションにインポートできます。 この .msi ファイルを使用すると、コンピューターにアプリケーションをインストールすることもできます。  
  
## <a name="exporting-a-policy"></a>ポリシーをエクスポートします。  
 管理コンソールを使用して、BizTalk グループまたはアプリケーションのポリシーをエクスポートすると、ポリシー情報を格納した .xml ポリシー ファイルが生成されます。 このポリシー ファイルを別の BizTalk グループにインポートしてそこにポリシーを作成し、そのグループのアプリケーションがポリシーを使用できるようにすることができます。 また、アプリケーションのポリシー情報は、BTSTask を使用してエクスポートすることもできます。 ただし、BTSTask にはポリシーの .xml ファイルをエクスポートするコマンドはありません。 代わりに、ポリシーのみを含むアプリケーションの .msi ファイルをエクスポートできます。 その後、別のグループのアプリケーションにその .msi ファイルをインポートできます。  
  
## <a name="exporting-bindings"></a>バインドのエクスポート  
 管理コンソールまたは BTSTask を使用して、BizTalk グループ、アプリケーション、またはアセンブリのバインドをエクスポートできます。 エクスポートを行うと、BizTalk Server によって、グループ、アプリケーション、またはアセンブリのバインド情報を含む .xml ファイルが生成されます。 バインドをエクスポートするときは、グループのグローバル パーティ情報もエクスポートできます。 その後、このバインド ファイルをアプリケーションに追加したり、BizTalk グループまたはアプリケーションにインポートしたりできます。  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [アプリケーションにバインド ファイルを追加する方法](../core/how-to-add-a-binding-file-to-an-application2.md)