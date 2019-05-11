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
ms.openlocfilehash: 90ab32fb2931f8a0294356e94d9f80f29b5b7c84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258510"
---
# <a name="what-happens-when-artifacts-are-exported"></a>アイテムのエクスポート時の動作
このトピックでは、成果物をエクスポートするときの動作について説明します。 このトピックで説明されている成果物をエクスポートする 3 つの方法はあります。  
  
-   BizTalk アプリケーションとそのアイテムを BizTalk .msi (Windows インストーラー) ファイルにエクスポート  
  
-   ポリシーを .xml ファイルにエクスポートします。  
  
-   バインドを .xml ファイルにエクスポート  
  
## <a name="exporting-a-biztalk-application"></a>BizTalk アプリケーションをエクスポートします。  
 BizTalk アプリケーションとが含まれているアイテムをエクスポートするときに、アプリケーションの構成情報とアイテム データは、BizTalk の .msi ファイルにエクスポートされます。 ほとんどのアイテム データは、次の例外で、BizTalk 管理データベースからエクスポートされます。  
  
- ポリシー データは、グループのルール エンジン データベースからエクスポートされます。  
  
- 仮想ディレクトリのデータは、管理データベースが存在しない場合、インターネット インフォメーション サービス (IIS) メタベースからエクスポートされます。 仮想ディレクトリが明示的に追加されていないアプリケーションと、ケースになります (」の説明に従って[仮想ディレクトリをアプリケーションに追加する方法](../core/how-to-add-a-virtual-directory-to-an-application.md)) またはアプリケーションが .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされました。  
  
- 管理データベースが存在しない場合、ローカル コンピューターでは、その他のユーザーの証明書ストアから証明書データがエクスポートされます。 証明書が明示的に追加されていないアプリケーションと、ケースになります (」の説明に従って[アプリケーションに証明書を追加する方法](../core/how-to-add-a-certificate-to-an-application.md)) またはアプリケーションがされた .msi ファイルからこのグループにインポートされていません。別の BizTalk グループからエクスポートされます。 関連付けられている証明書を持つ受信ポートでアプリケーションをエクスポートするときに、証明書がエクスポートされます。 エクスポート時に証明書から秘密キーが削除されます。  
  
  この .msi ファイルを使用して、別の BizTalk グループ内のアプリケーションも含めてすべてのデータ、アプリケーションのアイテムをインポートすることができます。 コンピューターでアプリケーションをインストールするのにこの .msi ファイルを使用することもできます。  
  
## <a name="exporting-a-policy"></a>ポリシーをエクスポートします。  
 BizTalk グループまたはアプリケーションのポリシーをエクスポートする管理コンソールを使用する場合は、ポリシー情報を含む .xml ポリシー ファイルが生成されます。 グループ内のアプリケーションで使用できるように、ポリシーを作成する別の BizTalk グループにこのポリシー ファイルをインポートできます。 BTSTask を使用して、アプリケーションのポリシー情報をエクスポートすることもできます。 ただし、BTSTask には、ポリシーの .xml ファイルをエクスポートするコマンドはありません。 代わりに、ポリシーのみを含んでいるアプリケーションの .msi ファイルをエクスポートすることができます。 別のグループ内のアプリケーションを .msi ファイルをインポートできます。  
  
## <a name="exporting-bindings"></a>バインドのエクスポート  
 管理コンソールまたは BTSTask を使用して、BizTalk グループ、アプリケーション、またはアセンブリのバインドをエクスポートすることができます。 これを行うと、BizTalk Server は、グループ、アプリケーション、またはアセンブリのバインド情報を含む .xml ファイルを生成します。 バインドをエクスポートするときに、グループのグローバル パーティ情報をエクスポートすることもできます。 アプリケーションにこのバインド ファイルを追加するか、BizTalk グループまたはアプリケーションにインポートします。  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md)   
 [BizTalk アプリケーション、バインド、およびポリシーのインポート](../core/importing-biztalk-applications-bindings-and-policies.md)   
 [アプリケーションにバインド ファイルを追加する方法](../core/how-to-add-a-binding-file-to-an-application2.md)