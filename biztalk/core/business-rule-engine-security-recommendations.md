---
title: ビジネス ルール エンジンのセキュリティに関する推奨事項 |Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
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
ms.openlocfilehash: 2ca5506d8ed9acab63e32a4ec86b057a4b775b63
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752754"
---
# <a name="business-rule-engine-security-recommendations"></a>ビジネス ルール エンジンのセキュリティに関する推奨事項
ビジネス ルール エンジンは、ビジネス ルール フレームワークのランタイム コンポーネントです。 ビジネス ルール フレームワークを使用すると、非常に判読しやすく意味論的にも充実した宣言型のルールを、任意のビジネス オブジェクト (.NET コンポーネント)、XML ドキュメント、またはデータベース テーブルに接続することができます。 ビジネス ルール フレームワークの詳細については、[を使用してビジネス ルールの作成と](../core/creating-and-using-business-rules.md)を参照してください。 ビジネス ルール エンジンの詳細については、[ルール エンジン](../core/rule-engine.md)を参照してください。  
  
 ビジネス ルール エンジンに対応する Windows ユーザー グループはなく、あるのは個別のアカウントのみです。 BizTalk Server では、2 種類の SQL Server ロールを使用して、ビジネス ルール エンジンへのアクセスを制限します。  
  
 RE_Admin_Users SQL Server ロールは、ビジネス ルール エンジンでルールの展開などの管理タスクを実行する必要があるユーザーのためのロールです。 RE_Admin_Users SQL Server ロールのメンバーには、BizTalk Server 管理者が含まれます。  
  
 RE_Host_Users グループは、ビジネス ルール エンジンを使用するその他すべてのユーザーのためのロールで、管理ユーザー権限を必要としないルールの読み取りや実行などのタスクを行うユーザーに適しています。 RE_Host_Users ロールのメンバーには、BizTalk_Host_Users ロールが含まれます。 SQL Server ロールを使用することで、BizTalk Server のアクセス許可とは別に、ビジネス ルール エンジンのアクセス許可を実装することができます。 ビジネス ルール エンジンを使用するために必要な最小限のアクセス許可の詳細については、[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)を参照してください。 ビジネス ルール エンジンをセキュリティで保護して環境に展開するには、次のガイドラインに従うことをお勧めします。  
  
-   BizTalk Server は、更新サービスのインストール時のアカウントにサービスとしてログオンする権限を与え、そのアカウントをビジネス ルール エンジン データベースの RE_Host_Users SQL Server ロールに追加します。 インストール時のアカウントが更新サービスの実行に使用するアカウントと同一でない場合は、RE_Host_Users SQL Server ロールからインストール アカウントを削除する必要があります。  

-   別の BizTalk ホスト サービス アカウントとして同じアカウントを使用しない場合も BizTalkMgmtDb、BizTalkMsgBoxDb で BTS_HOST_USERS をルール エンジンのサービス アカウントを追加します。

-   更新サービス コンポーネントを使用する場合は、BizTalk ランタイム コンピューターにインストールする必要があります。 ルール エンジン データベースからルールを取得するために、更新サービスはサービスの呼び出し元の権限を借用します。  
  
-   既定では、ルール エンジンのアイテムに対するアクセス権のレベルはすべての BizTalk ホストで同一になっています。 セキュリティに関してホスト単位での区別はありません。 ルール エンジンの API を使用することで、ポリシー単位のセキュリティを構成することができます。 ポリシーごとのセキュリティを構成する方法の詳細については、[ビジネス ルール フレームワークのセキュリティ](../core/business-rules-framework-security.md)を参照してください。  
  
## <a name="see-also"></a>参照  
 [処理サーバーのポート](../core/ports-for-the-processing-servers.md)
