---
title: アプリケーションの展開に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e5fb4f6-f9bd-4322-93f9-723e9e3c3317
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4bc6f54ad0ce3c355d8d6aad9a09e24387ec7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395820"
---
# <a name="known-issues-with-deploying-an-application"></a>アプリケーションの展開に関する既知の問題
## <a name="deploying-a-biztalk-application"></a>BizTalk アプリケーションの展開  
 **更新されたアプリケーションをデプロイする場合は、参照を修正する必要があります。**  
  
 既存のアプリケーションを置換するまったく新しいアプリケーションを展開する場合は、他のアプリケーションと交換するアプリケーションの間の参照を修正する必要があります。  
  
 **Visual Studio を使用してアプリケーションを展開するアプリケーションを停止できます。**  
  
> [!NOTE]  
>  運用環境にアプリケーションを配置する Visual Studio を使用しないことをお勧めします。  
  
 関連付けられていないものも含め、アプリケーションを展開するときに場合、Visual Studio を使用して、運用環境にアプリケーションを配置して、ホスト インスタンスを再起動オプションは、プロジェクト プロパティでは、すべてのホスト インスタンスは True に設定が再起動されます。このアプリケーション。 ローカル コンピューター上の任意のホスト インスタンスで実行されているその他のすべてのアプリケーションを停止します。  
  
## <a name="adding-artifacts-to-a-biztalk-application"></a>BizTalk アプリケーションにアイテムを追加します。  
 **依存関係を移動できるアイテムの移動します。**  
  
 新しいアプリケーションにアイテムを移動すると依存関係が存在するその他のアイテムが、新しいアプリケーションに移動した成果物が依存するアイテムを含むアプリケーションへの参照がない限り、移動されます。 また、移動先のアイテムに依存関係のあるすべてのアイテムも移動されます、アプリケーションがそれらを含む新しいアプリケーションへの参照のない限り。 成果物を移動するときに移動することも、他の成果物の一覧が表示されます。 アイテムの移動手順については、次を参照してください。[を別のアプリケーション アイテムの移動方法](http://go.microsoft.com/fwlink/?LinkId=154999)(http://go.microsoft.com/fwlink/?LinkId=154999)します。  
  
## <a name="exporting-a-biztalk-application"></a>BizTalk アプリケーションをエクスポートします。  
 **Windows Vista で .msi ファイルをインストールするときに、不適切なエラーが表示されることができます。**  
  
 使用してエクスポートされた .msi パッケージをインストールするときに[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]Windows Vista® で実行されている BizTalk Server で、次の誤ったエラーが表示される、"インストーラーはこのパッケージをインストールして予期しないエラーにしました。 このパッケージに問題がある可能性があります。 エラー コード: 2869。" このエラーを修正するには、BizTalk Server を使用してパッケージを最初にインポートし再エクスポートし、パッケージをインストールします。  
  
## <a name="importing-a-biztalk-application"></a>BizTalk アプリケーションをインポートします。  
 **パスワードは、バインド、アプリケーションに追加されたファイルは削除されません。**  
  
 セキュリティ上の理由により、パスワードは、アプリケーションのエクスポート中にアプリケーションのバインドから削除されます。 ただし、既にアプリケーションに追加されたバインド ファイルからは削除されません。 アプリケーションをインポートした後、アプリケーションを機能させるためにパスワードを再構成する必要があります。 これは、バインド ファイルを編集するか、管理コンソールを使用して行んだことができます。 バインド ファイルの編集の詳細については、次を参照してください。[バインド ファイルのカスタマイズ](http://go.microsoft.com/fwlink/?LinkId=155000)(http://go.microsoft.com/fwlink/?LinkId=155000)します。 アダプターのセキュリティ構成の詳細については、次を参照してください。[を使用してアダプター](http://go.microsoft.com/fwlink/?LinkId=155001) (http://go.microsoft.com/fwlink/?LinkId=155001)します。  
  
 **BizTalk Server ではありませんロールバック スクリプト化されたインポートまたはインストール**  
  
 インポートが失敗すると、BizTalk Server によりカスタム スクリプトによって実行される操作を除くすべてのインポート操作がロールバックされます。 これによりのインストールにも該当し、操作をアンインストールします。  
  
 **不足しているスキーマは、インポート後に報告されない可能性があります。**  
  
 別のアプリケーションのプロパティ スキーマを使用するアプリケーションの送信ポートにフィルターを作成し、そのアプリケーションを新しい BizTalk グループにインポートした場合、そのアプリケーションをインストールおよび起動しても、フィルターは正しく機能せず、スキーマが欠落していることを伝える警告も発生しません。 この問題は、スキーマが欠落しているアプリケーションをインストールする前に、必要なスキーマを含んでいるアプリケーションをインポートすれば解決できます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開](../technical-guides/deploying-an-application.md)