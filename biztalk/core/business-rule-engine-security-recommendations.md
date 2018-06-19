---
title: ビジネス ルール エンジンのセキュリティに関する推奨事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, business rules
- Business Rules Framework, security
- business rules, security
ms.assetid: d5df1cd0-112a-4c72-b95d-cbcd1bc6a2c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d7402a1cc36ef3d9473c3303da79b0c23f46bf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231946"
---
# <a name="business-rule-engine-security-recommendations"></a>ビジネス ルール エンジンのセキュリティに関する推奨事項
ビジネス ルール エンジンは、ビジネス ルール フレームワークのランタイム コンポーネントです。 ビジネス ルール フレームワークを使用すると、非常に判読しやすく意味論的にも充実した宣言型のルールを、任意のビジネス オブジェクト (.NET コンポーネント)、XML ドキュメント、またはデータベース テーブルに接続することができます。 ビジネス ルール フレームワークの詳細については、次を参照してください。[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)です。 ビジネス ルール エンジンの詳細については、次を参照してください。[ルール エンジン](../core/rule-engine.md)です。  
  
 ビジネス ルール エンジンに対応する Windows ユーザー グループはなく、あるのは個別のアカウントのみです。 BizTalk Server では、2 種類の SQL Server ロールを使用して、ビジネス ルール エンジンへのアクセスを制限します。  
  
 RE_Admin_Users SQL Server ロールは、ビジネス ルール エンジンでルールの展開などの管理タスクを実行する必要があるユーザーのためのロールです。 RE_Admin_Users SQL Server ロールのメンバーには、BizTalk Server 管理者が含まれます。  
  
 RE_Host_Users グループは、ビジネス ルール エンジンを使用するその他すべてのユーザーのためのロールで、管理ユーザー権限を必要としないルールの読み取りや実行などのタスクを行うユーザーに適しています。 RE_Host_Users ロールのメンバーには、BizTalk_Host_Users ロールが含まれます。 SQL Server ロールを使用することで、BizTalk Server のアクセス許可とは別に、ビジネス ルール エンジンのアクセス許可を実装することができます。 ビジネス ルール エンジンを使用するために必要な最小限のアクセス許可の詳細については、次を参照してください。[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)です。 ビジネス ルール エンジンをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
-   BizTalk Server は、更新サービスのインストール時のアカウントにサービスとしてログオンする権限を与え、そのアカウントをビジネス ルール エンジン データベースの RE_Host_Users SQL Server ロールに追加します。 インストール時のアカウントが更新サービスの実行に使用するアカウントと同一でない場合は、RE_Host_Users SQL Server ロールからインストール アカウントを削除する必要があります。  
  
-   更新サービス コンポーネントを使用する場合は、BizTalk ランタイム コンピューターにインストールする必要があります。 ルール エンジン データベースからルールを取得するために、更新サービスはサービスの呼び出し元の権限を借用します。  
  
-   既定では、ルール エンジンのアイテムに対するアクセス権のレベルはすべての BizTalk ホストで同一になっています。 セキュリティに関してホスト単位での区別はありません。 ルール エンジンの API を使用することで、ポリシー単位のセキュリティを構成することができます。 ポリシー単位のセキュリティを構成する方法の詳細については、次を参照してください。[ビジネス ルール フレームワークのセキュリティ](../core/business-rules-framework-security.md)です。  
  
## <a name="see-also"></a>参照  
 [処理サーバーのポート](../core/ports-for-the-processing-servers.md)