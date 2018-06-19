---
title: 一般的な質問と回答のトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2f89d92-0a97-4017-8b8e-6afd8b20eaf4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37e63f8838dea7adee91b5b43b2bc881cb53eae1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247106"
---
# <a name="general-troubleshooting-questions-and-answers"></a>一般的なトラブルシューティングに関する質問と回答
このトピックには質問と回答は、BizTalk マッパーでの問題を解決するのに役立ちます。  
  
## <a name="how-do-i-specify-xslt-output-settings"></a>XSLT 出力の設定を指定する方法を教えてください。  
 BizTalk マッパーで、XML 宣言を含めるかどうかを指定し、出力インスタンス データで使用するエンコードを制御できます。  
  
#### <a name="include-or-exclude-an-xml-declaration"></a>XML 宣言のエクスクルードまたはインクルード  
  
1.  グリッド ビューで、マッパー グリッドをクリックします。 **プロパティ**ウィンドウにグリッドのプロパティが表示されます。  
  
2.  ドロップダウン リストで、 **XML 宣言の省略**プロパティを選択 **[はい]** XML 宣言を省略するか選択**いいえ**XML 宣言を省略するされません。  
  
#### <a name="set-encoding-for-output-instance-data"></a>出力インスタンス データのエンコードを設定します。  
  
1.  グリッド ビューで、マッパー グリッドをクリックします。 **プロパティ**ウィンドウにグリッドのプロパティが表示されます。  
  
2.  ドロップダウン リストで、 **XSLT エンコード**出力インスタンス データに使用するプロパティ、文字セットを選択します。  
  
## <a name="how-do-i-create-multipart-mappings"></a>マルチパート マッピングを作成するにはどうすればよいですか。  
 一緒に使用する複数のマップがある場合は、それらを使用して、オーケストレーションに結合する必要があります、**変換**図形を一緒にそれらをテストします。 BizTalk マッパーで一度にテストできるのは 1 つのマップだけです。  
  
## <a name="why-isnt-my-database-functoid-working"></a>データベース Functoid が動作しないのはなぜですか。  
 データベース functoid**データベース検索**と**値抽出**は、エラー情報を直接返さない情報をキャプチャするを指定して、代わりに、**エラーを返す** functoid マップで使用します。 使用することができます、**エラーを返す**functoid は、次のシナリオと同様に、エラー検出のため。  
  
-   マップが持っている場合、**データベース検索**または**値抽出**functoid が期待どおりに動作していないこと。 エラー メッセージを表示するには、この Functoid を出力スキーマのフィールドに一時的にマップしてください。  
  
-   データベース操作が失敗したときに、アプリケーションで別のメッセージ内容が要求された場合。 使用することができます、**エラーを返す**functoid をエラーを検出し、ダウン ストリーム アプリケーションが適切な方法で対処できるように、エラー メッセージを代替構造にマップします。  
  
 実行時にのみが検出されたエラーを回避することを確認する最初のパラメーター、**エラーを返す**functoid の出力は、**データベース検索**functoid とその他の functoid に出力できません、データベースのカテゴリ。  
  
 使用しての詳細については、**エラーを返す**functoid (サンプルを含む) を参照してください、 **Functoid リファレンス**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="why-is-my-map-failing-when-calling-my-custom-functoid"></a>カスタム Functoid を呼び出すとマップで障害が発生するのはなぜですか。  
 マップでカスタム Functoid を呼び出せるようにするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] コンピューターのグローバル アセンブリ キャッシュ (GAC) にそれらのカスタム Functoid をインストールしておく必要があります。 カスタム Functoid を含むアセンブリが署名されており、GAC に配置されていることを確認してください。 また、アセンブリを "%BTSINSTALLPATH%\Developer Tools\Mapper Extensions" フォルダーにコピーします。  
  
 アセンブリを GAC にインストールの詳細については、次を参照してください。 [GAC にアセンブリのインストール](../core/assembly-installation-in-the-gac.md)です。 GAC にインストールされたアセンブリを表示するには、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] のインストール ディレクトリの Assembly ディレクトリに移動します。  
  
## <a name="see-also"></a>参照  
 [マップのトラブルシューティング](../core/troubleshooting-maps.md)